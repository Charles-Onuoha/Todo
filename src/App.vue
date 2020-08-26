<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/Header/Head'; 
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    Header,
   Todos,
   AddTodo,
   
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Eat",
          completed: false
        },

        {
          id: 2,
          title: "Wash The Car",
          completed: false
        },

        {
          id: 3,
          title: "Sleep",
          completed: false
        }
      ]
    }
  }, 
  methods: {
  deleteTodo(id) {
    this.todos = this.todos.filter(todo => todo.id !== id);
  },
  addTodo(newTodo) {
    this.todos = [...this.todos, newTodo];
  }
}
}
</script>

<style>
* {
   box-sizing: border-box;
   margin: 0;
   padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4; 
  background-color: blueviolet;
}

</style>
