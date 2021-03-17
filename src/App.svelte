<script>
	let username = "goku";

	function clearUsername() {
		username = "";
	}
</script>

<main>
<form>
	<h1>Hello, {username.toUpperCase()}!</h1>
	<h2>Username is {username.length} characters</h2>
	<button type="button" on:click={clearUsername}>Clear Username</button>
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