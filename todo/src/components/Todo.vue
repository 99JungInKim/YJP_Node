<template>
  <div class="hello">
    <h1>Todo</h1>
    <div><input type="text" id = "inputText" @keyup.enter="addTodo"><button @click="addTodo">Add</button></div>
    <div>{{todos}}</div>
    <table>
      <tr v-for="(todo, i) in todos" :key="i">
        <td>{{todo}}</td>
        <td><button @click="deleteTodo(i)">X</button></td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'ToDo',
    data(){
    return {
      todos:[]
    }
  },props:{

  },
  methods: {
    addTodo(){
      this.todos.push(document.getElementById("inputText").value)
    },
    deleteTodo(i){
      console.log(i)
      this.todos.splice(i,1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
