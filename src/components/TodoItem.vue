<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            <button @click="$emit('del-todo', todo.id)" class="del">Delete</button>
            {{todo.title}}</p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
    
}
</script>

<style scoped>

.todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
    width: 700px;
    position: relative;
    top: 170px;
    left: 23%;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 10%; 
    cursor: pointer;
    float: right;
    outline: none  ;
  }
</style>