<template>
    <div>
        <form @submit.prevent="addTodo">
            <input type="text" v-model="title" placeholder="What Do You Need To Do?">
            <input type="submit" value="Add Todo" class="btn">
        </form>
    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
    name: "AddTodo",
    data() {
        return {
             title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false 
            }

            this.$emit('add-todo', newTodo);
        }
    }
}
</script>

<style scoped>
form {
    display: flex;
  }
  input[type="text"] {
    width: 600px;
    padding: 5px;
    position: relative;
    left: 293px;
    height: 50px;
    border-radius: 10px;
    outline: none;
    top: 110px;
    font-family: Arial, Helvetica, sans-serif;
    font-size: medium;
  }
  input[type="submit"] {
    width: 100px;
    position: relative;
    left: 300px;
    top: 110px; 
    height: 50px;
    border-radius: 10px;
    outline: none;
    color: blueviolet;
    font-size: medium;
  }

  .submit:hover{
      color: black;
      background-color: blueviolet;
  }
</style>
