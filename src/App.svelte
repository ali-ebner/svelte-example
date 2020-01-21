<script>
	export let name;
	export let data;
	let value = 'Some random form field';

	function onRemove(index) {
		let newData = [...data];
		newData.splice(index, 1);
		data = newData;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	{@debug data}
	 <div className="p-2 text-center">
    <input type="text" value={value} />
  </div>
	{#each data as datum, i}
		<div className="memo-tile m-2">
      <div className="justify-content-between flex-nowrap p-4">
        <div className="p-2">
          <img src={datum.picture} alt={datum.firstName + ' ' + datum.lastName} />
        </div>
        <div className="p-2">
          <button className="remove text-center" on:click={() => onRemove(i)}>&times;</button>
          <div>Name: <span>{datum.firstName} {datum.lastName}</span></div>
          <div>Age: <span>{datum.age}</span></div>
          <div>Email Address: <span>{datum.email}</span></div>
          <div>Phone Number: <span>{datum.phone}</span></div>
          <div>Company: <span>{datum.company}</span></div>
          <div>Address: <span>{datum.address}</span></div>
          <div>Registration Date: <span>{datum.registered}</span></div>
          <div>About {datum.firstName} {datum.lastName}: <span>{datum.about}</span></div>
        </div>
      </div>
    </div>
	{/each}
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