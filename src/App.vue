<template>
  <div id="app">
    <form v-on:submit.prevent="saveNewToDo">
      <label for="new-task">Add a new ToDo:</label>
      <input id="new-task" type="text" v-model="newTask"/>
      <input type="radio" name="priority" value="high">High
      <input type="radio" name="priority" value="low>">Low
      <input type="submit" value="Save new task"/>
    </form>
    <ul>
      <li v-for="task in tasks"> {{ task }} </li>
    </ul>
  </div>
</template>

<script>
export default {
  data(){
    return{
      tasks: ['Hoover', 'Dust', 'Washing'],
      
      newTask: ''
  }
},
  methods: {
    saveNewToDo: function(){
      this.tasks.push(this.newTask);
      this.newTask ='';
    }
  }    
}

</script>

<style>

</style>
