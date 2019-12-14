<script>
  import Word from './Word.svelte';
  export let data;

  $: parsed = parseData(data)
                .reduce(
                  (acc, item) => Array.isArray(item) 
                  ? [...acc, ...item] 
                  : (item ? [...acc, item] : acc), 
                []);

  function parseData (data) {
    if (typeof data === 'string') return ([{ main: data, tips: null }]);
    if (Array.isArray(data)) return data.map(parseData);
    if (data && data.main) return data;
    return null;
  }
</script>

<div>
  {#each parsed as word}
    <Word bind:data={word} />
  {/each}
</div>

<style>

</style>