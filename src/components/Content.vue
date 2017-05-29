<template>
	<div>
		hello this is content file
		<div>
			<ul>
				<li v-for="todo in todos" class="todo">
					<div :class="{active: todo.completed }">
					{{ todo.text }}
					<button v-on:click="completeTodo(todo.id)">Completed</button>
					<button v-on:click="deleteTodo(todo.id)">Delete</button>
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
      var index = this.todos.findIndex(function (o) {
        return o.id === id
      })
      this.todos.splice(index, 1)
    },
    completeTodo: function (id) {
      var index = this.todos.findIndex(function (o) {
        return o.id === id
      })
      this.todos[index].completed = true
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
