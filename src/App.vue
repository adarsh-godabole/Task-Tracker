<template>
  <div class="container">
    <Header  @show-add-task="showTask" title="Task Tracker"/>
    <AddTask v-show="showAddTask" @add-task="addTask"/>
    <Tasks @toggle-reminder="togglereminder" @delete-task="deleteTask" :tasks="tasks"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Tasks from './components/Tasks.vue';
import AddTask from './components/AddTask.vue';


export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  },
  data(){
    return{
      tasks:[],
      showAddTask:false
    }
  },
  methods:{
    addTask(newTask){
      this.tasks=[...this.tasks,newTask]
    },
    showTask(){
      this.showAddTask=!this.showAddTask;
    },
    deleteTask(id)
    {
      console.log("ID"+id);
      this.tasks=this.tasks.filter((task) =>  task.id !== id)
    },
    togglereminder(id)
    {
      this.tasks = this.tasks.map(
        (task) => task.id===id ? {...task,reminder:!task.reminder}: task
      );
    }
  },
  created(){
    this.tasks = [
      {
        id:1,
        text:'Walking',
        day:'29/09/2021',
        reminder:true
      },
      {
        id:2,
        text:'Gym',
        day:'29/09/2021',
        reminder:false
      }

    ]
    // console.log(this.tasks[0]);
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}

</style>
