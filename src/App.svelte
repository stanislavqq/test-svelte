<script>
	import ColorBlock from './ColoredBlock.svelte';
	let blocks;
	blocks = [
		{id: 1},
		{id: 2, color: 'red', opacity: 1},
		{id: 3, color: 'blue', opacity: 1},
		{id: 4, color: 'green', opacity: 1},
	];

	function clickBlock(id){
		let index = blocks.findIndex((item) => item.id === id);
		blocks.filter(item => item.id !== id).forEach(item => item.opacity = 1);

		if (blocks[index].opacity > 0) {
			blocks[index].opacity = 0;
		} else {
			blocks[index].opacity = 1;
		}
	}
</script>

<main>
	<div class="container">
		{#each blocks as block (block.id)}
			<ColorBlock on:click={clickBlock(block.id)} bind:color={block.color} bind:opacity={block.opacity}/>
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

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>