<script>
	import Sentence from './Sentence.svelte';

	export let name;
	// let sentence = 'I see the world!'
	let sentences = [
		['I', { main: 'go', tips: ['go', 'went', 'gone'] }, 'to cinema!'],
		['I', { main: 'am', tips: ['am', 'are', 'is'] }, { main: 'going' }, 'to cinema!'],
		['I', { main: 'have', tips: ['have', 'have', 'has'] }, 'been', { main: 'going' }, 'to cinema!'],
	]
</script>

<main>
	<h1>Hello {name}!</h1>
	<div class="wrapper">
		{#each sentences as sentence}
			<div class="item-wrapper">
				<Sentence data={sentence} />
			</div>
		{/each}
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	.item-wrapper {
		margin-bottom: 2em;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>