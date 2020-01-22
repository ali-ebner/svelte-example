<script>
  export let datum;
  export let onRemove;
</script>

<main class="memo-tile">
  <div class="tile-body">
    <div class="p-2">
      <img src={datum.picture} alt={datum.firstName + ' ' + datum.lastName} />
    </div>
    <div class="p-2">
      <button class="remove text-center" on:click={() => onRemove(datum.guid)}>&times;</button>
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
</main>

<style>
  .tile-body {
    justify-content: space-between;
    display: flex;
  }

	.memo-tile {
  background-color: #fff;
  border-radius: 5px;
  color: #000;
  height: 250px;
  max-width: 45%;
  overflow-y: auto;
  margin: 5px;
}

	.remove {
  background-color: lightgray;
  border-radius: 50%;
  cursor: pointer;
  display: inline-block;
  margin-left: calc(100% - 30px);
  width: 22px;
}

	.remove:hover {
  background-color: gray;
  color: #fff;
	}
</style>