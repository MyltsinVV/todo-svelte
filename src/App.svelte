<script>
	import Todo from './Todo.svelte';
	import Form from './Form.svelte';

	let todos = [
		{ id: 1, name: 'Купить молоко', isDone: true },
		{ id: 2, name: 'Купить хлеб', isDone: false }
	];

	function addTodo(value) {
		todos = [
			...todos,
			{
				id: Date.now(),
				name: value,
				isDone: false,
			}
		]
	}

	function removeTodo(id) {
		todos = todos.filter(todo => todo.id !== id);
	}
</script>

<Form {addTodo}/>
<hr>
{#each todos as todo, index (todo.id)}
	<Todo {removeTodo} {...todo} />
{:else }
	<b>Создай задачу!</b>
{/each}
