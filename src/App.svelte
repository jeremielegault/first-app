<script>
	import ContactCard from "./ContactCard.svelte";

	let name = "Jeremie";
	let age = 30;
	let jobTitle = "";
	let description = "";
	let image = "";
	$: uppercaseName = name.toUpperCase();
	$: console.log(name);
	$: if (name === "Jeremie Legault") {
		age = 45;
	}
	function incrementAge() {
		age += 1;
	}
	function changeName() {
		name = "Jeremie Legault";
	}

	function nameInput(event) {
		const enteredValue = event.target.value;
		name = enteredValue;
	}
</script>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<!-- <button on:click={changeName}>Change Name</button> -->
<!-- <input type="text" value={name} on:input={nameInput} /> -->
<input type="text" bind:value={name} />
<input type="text" bind:value={jobTitle} />
<input type="text" bind:value={description} />
<input type="text" bind:value={image} />

<ContactCard userName={name} {jobTitle} {description} {image} />

<style>
	h1 {
		color: purple;
	}
</style>
