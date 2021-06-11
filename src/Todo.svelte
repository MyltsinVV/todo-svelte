<script>
	export let id;
	export let name;
	export let isDone;
	export let removeTodo;
</script>

<style>
	.todo {
		border: 1px solid black;
		border-radius: 2px;
		padding: 1rem;
    margin-bottom: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
	}

	.done {
    text-decoration: line-through;
	}

	.remove-todo {
		background: red;
    color: #fff;
	}
</style>

<div class="todo">
	<div>
		<input type="checkbox" bind:checked={isDone}>
		<span class:done={isDone}>{name}</span>
	</div>
	<button class="remove-todo" on:click={removeTodo(id)}>Remove Todo</button>
</div>
