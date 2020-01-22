<script>
	import TileList from './TileList.svelte';
	export let data;
	let value = 'Some random form field';
	let showExercise = false;
</script>

<main>
	<button on:click={() => showExercise = !showExercise}>{showExercise ? 'Unmount' : 'Mount'} Exercise</button>
	<div class="p-2 text-center">
    <input type="text" bind:value={value} />
  </div>
	{#if showExercise}
		<TileList data={data} />
	{/if}
</main>

<style>
	button {
		margin-top: 10px;
	}
	main {
		background-color: black;
		height: 100%;
		width: 100%;
		text-align: center;
	}
</style>
