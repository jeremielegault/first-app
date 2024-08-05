<script>
	let name = "Jeremie";
	let age = 30;

	$: uppercaseName = name.toUpperCase();

	function incrementAge() {
		age += 1;
	}
	function changeName() {
		name = "Jeremie Legault";
	}
</script>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<button on:click={changeName}>Change Name</button>

<style>
	h1 {
		color: purple;
	}
</style>
