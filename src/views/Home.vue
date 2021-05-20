<template>
  <div id="app">
   <AddTodo @add-todo="addTodo" />
   <Todos :todos="todos" @del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from '../components/Todos';
import AddTodo from '../components/AddTodo';

export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo
  },
  data(){
    return{
      todos: []
    }
  },
  methods: {
    deleteTodo(id){

      fetch(`https://jsonplaceholder.typicode.com/todos/${id}`, {
        method: 'DELETE',
        headers: {
          'Accept': 'application/json, text/plain, */*',
          'Content-type': 'application/json'
        }
      })
      .then(res => res.json())
      .then(data => console.log(data))
      .catch(err => console.log(err));

      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      const { title, completed } = newTodo;

      fetch('https://jsonplaceholder.typicode.com/todos', {
        method: 'POST',
        headers: {
          'Accept': 'application/json, text/plain, */*',
          'Content-type': 'application/json'
        },
        body: JSON.stringify({title:title, completed: completed})
        })
      .then(res => res.json())
      .then(data => console.log(data))
      .catch(err => console.log(err));


        this.todos = [...this.todos, newTodo];
      }
  },
  created(){
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=6')
    .then(res => res.json())
    .then(data => this.todos = data)
    .catch(err=> console.log(err));
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
  width: 65%;
  margin: auto;
}

.btn {
  display: inline-block;
  border: none;
  background: #2c3e50;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #384f66;
}
</style>

