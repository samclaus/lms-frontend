<script lang="ts">
	import Button from "@smui/button/styled";
	import TextField from "@smui/textfield/styled";
	import HelperText from "@smui/textfield/helper-text/styled";

	let username = "";
	let password = "";

	function login(event: Event): void {
		// Stop the browser from submitting the HTML form and doing old-fashioned SSR stuff
		event.preventDefault();
		
		const ws = new WebSocket(`wss://${window.location.host}/connect`);
		
		ws.addEventListener("open", function() {
			ws.send(JSON.stringify({
				username,
				password: btoa(password)
			}))
		})

		
	}
</script>

<svelte:head>
	<!-- Change the page title when we are on the login screen -->
	<title>Edify | Login</title>
</svelte:head>

<main>
	<h1>Login to Edify</h1>
	<form on:submit={login}>
		<div>
			<TextField variant="filled" label="Username" bind:value={username}/>
			<HelperText persistent slot="helper">You may also login using your email</HelperText>
		</div>
		<div>
			<TextField variant="filled" label="Password" bind:value={password} type="password"/>
		</div>
		<div>
			<Button type="submit">Login</Button>
			<Button type="reset">Reset</Button>
		</div>
	</form>
</main>

<style>
	main {
		text-align: center;
		margin: 0 auto;
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
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