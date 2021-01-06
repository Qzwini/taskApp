<template>
  <div class="home">
    <h3> {{ title }} </h3>

<Tasks :tasks="tasks" v-on:completeTaskEvent="completeTask" v-on:deleteTaskEvent="deleteTask"></Tasks>
<input @keyup.enter="addNewTask" type="text" class="form-control mb-2"  v-model="newTask">
<button v-on:click="addNewTask" class="btn btn-success btn-block"> Add New Tassk</button>
 


  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Tasks from '../components/tasks.vue'

export default {
  
  name: 'Home',
  components: {
    Tasks
  },
  data () {
return {
  title:" Tasks Apps",

newTask: null,

  tasks:[
    {
body:'Go to shop',
completed: false
  },
      {
body:'Go to barbar',
completed: false
  },
      {
body:'Go to school',
completed: false
  },
        {
body:'Go to bed',
completed: false
  },
    
  ]
}
  },

methods :{

addNewTask(){
if (this.newTask == null){}
else{
  this.tasks.push({
    body: this.newTask,
    completed: false
  });
  this.newTask = null;
  }},



completeTask(task){
  var mor=task.completed;
  mor = !mor;
  task.completed=mor;
},

deleteTask(index){
 this.tasks.splice(index, 1);
 
}

},
};
</script>

<style >

.home {
  margin-top: 30px;
}

i {
  padding-left: 10px;
}

input {
margin-top: 10px;
}


</style>