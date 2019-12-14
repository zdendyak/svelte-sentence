<script>
  import Hoverable from './Hoverable.svelte';
  export let data;

</script>

<Hoverable let:hovering={active}>
  <div>
    {#if active && data.tips && data.tips.length }
      <span class="tooltip">{data.tips.join(', ')}</span>
    {/if}
    <span class="word">{data.main}</span>&nbsp;
  </div>
</Hoverable>


<style>
  div {
    position: relative;
  }

  .tooltip {
    position: absolute;
    top: -1.75em;
    width: max-content;
    border: 1px solid #efefef;
    border-radius: 3px;
    padding: 3px;
    background-color: rgb(225, 250, 241);
  }
  .tooltip:after {
    background-color: rgb(225, 250, 241);
    content: '';
    left: 6px;
    border-right: 1px solid #efefef;
    border-bottom: 1px solid #efefef;
    width: .375em;
    height: .375em;
    display: block;
    position: absolute;
    transform: rotate(45deg);
  }
</style>