<script>
  import Tile from './Tile.svelte';
  export let data;

  function onRemove(guid) {
    data = data.filter((datum) => datum.guid !== guid);
	}
</script>

<main>
		{#each data as datum, i (datum.guid)}
      <Tile datum={datum} onRemove={onRemove} />
    {/each}
</main>

<style>
  main {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
    align-items: flex-start;
  }
</style>
