<template>
	<div class="container">
		<Header />
		<Aside />
		 <input v-model="newTodo" />
		 <button v-on:click="addTodo">Add</button>
		<Content
			v-bind:todos="todos"
		 />
	</div>
</template>

<script>
import Header from './Header'
import Aside from './Aside'
import Content from './Content'

export default {
  methods: {
    addTodo: function () { if (this.newTodo) this.todos.splice(0, 0, { id: this.todos.length, text: this.newTodo }); this.newTodo = undefined }
  },
  data () {
    return {
      msg: 'this is msg part',
      newTodo: undefined,
      todos: [{ id: 1, text: 34, completed: false }, { id: 1, text: 23434, completed: true }]
    }
  },
  components: {
    Header, Content, Aside
  }
}
</script>

<style scoped>
	.container {
		padding: 10px;
	}
</style>
