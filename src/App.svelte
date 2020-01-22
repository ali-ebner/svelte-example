<script>
	import TileList from './TileList.svelte';
	export let data;
	let value = '';
	let showExercise = false;
	$: message = showExercise ? 'Unmount Exercise' : 'Mount Exercise';
</script>

<main>
	<button on:click={() => showExercise = !showExercise}>{message}</button>
	{#if showExercise}
		<div>
			<input type="text" bind:value={value} placeholder='some random form field' />
		</div>
		<TileList data={data} />
	{/if}
</main>

<style>
	button {
		margin-top: 10px;
		background-color: rgb(0, 100, 200);
		color: white;
		border-radius: 5px;
	}
	main {
		background-color: black;
		height: 100%;
		width: 100%;
		text-align: center;
	}
</style>
