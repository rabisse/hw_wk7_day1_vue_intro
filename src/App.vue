<template>
  <div id="app">
    <h1>To-Do List:</h1>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        <span>{{task}}</span>
      </li>
    </ul>

    <form v-on:submit.prevent="saveNewTask">
      <label for="new-task">Add task:</label>
      <input type="text" id="new-task" v-model="newTask">
      <input type="submit" value="Save">
    </form>

  </div>
</template>

<script>
export default {
  data(){
    return {
      tasks: ["Finish homework", "Make dinner", "Have a beer"],
      newTask: ""
    }
  },
  methods: {
    saveNewTask: function() {
      this.tasks.push(this.newTask)
      this.newTask = ""
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

li {
  list-style: none;
}
</style>
