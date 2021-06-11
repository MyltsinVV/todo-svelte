<script>
	export let addTodo;
	let value = '';

	function submitHandler() {
		if (value.trim()) {
			addTodo(value);
			value = '';
		}
	}
</script>

<form on:submit|preventDefault={submitHandler}>
	<input type="text" bind:value>
	<button type="submit">Добавить todo</button>
</form>
