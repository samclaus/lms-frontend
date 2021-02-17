<script>
	let username = "goku"

	function clearusername(){
		username=""
	}
</script>

<main>
<form>
	<label>username:
		<input type="text" bind:value={username}>
	</label>
	<h1>{username}</h1>
	<button on:click={clearusername}>clear username</button>
</form>

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
		 
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>