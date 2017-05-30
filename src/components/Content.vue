<template>
	<div>
		hello this is content file
		<div>
			<ul>
				<li v-for="(todo,index)  in todos" class="todo">
					<div :class="{active: todo.completed }">
					{{ todo.text }}
					<button v-on:click="completeTodo(todo)">Completed</button>
					<button v-on:click="deleteTodo(index)">Delete</button>
					</div>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default {
  props: ['todos'],
  methods: {
    deleteTodo: function (id) {
      this.todos.splice(id, 1)
    },
    completeTodo: function (todo) {
      todo.completed = true
    }
  },
  data () {
    return {
      msg: 'message part'
    }
  }
}
</script>

<style>
	ul {
		list-style: none;
	}
	.todo {
		padding: 10px;
    background-color: #6a9de8;
    border: 1px solid #467fe6;
    margin-top: -1px;
    text-align: left;
	}
	.active {
		text-decoration: line-through;
	}
</style>
