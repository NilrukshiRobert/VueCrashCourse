<template>
<div class="container">
  <Header @toggle-add-task="toggleAddTask" 
  title="Task Tracker"  :showAddTask="showAddTask"/>
  <div v-show="showAddTask">
  <AddTask @add-task="addTask" />
  </div>
  <Tasks @toggle-reminder="toggleReminder"  @delete-task="deleteTask" :tasks="tasks" />
  </div>
  </template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'
import AddTask from './components/AddTask.vue'


export default {
   name:'App',
   components:{
     Header,
     Tasks,
     AddTask
   },
   data(){
     return{
       tasks:[],
       showAddTask:false,
     }
   },
   methods:{
     toggleAddTask(){
       this.showAddTask =!this.showAddTask
     },

     addTask(){
       this.tasks = [...this.tasks,task]
     },
     deleteTask(id){
       if(confirm('Are you sure?')){
         this.tasks= this.tasks.filter((task) => task.id !== id)
       } 
     },

     toggleReminder(id) {
      this.tasks = this .tasks.map((task) =>
      task.id === id ? {...task, reminder: !task.
      reminder } : task
      )
     },
     async fetchTasks(){
       const res = await fetch ('http://localhost:3000/tasks')
     
       const data = await res.json()

       return data
     }
   },
   async created(){
     this.tasks =  await this.fetchTasks()
   }
 }
</script>

<style>
  .btn{
    display: inline-block;
    background: darkblue;
    color:white;
    border: none;
    padding: 10px 20px;
    margin:5px;
    border-radius: 5px;
    cursor: pointer;
    text-decoration: none;
    font-size: 15px;
    font-family: inherit;
  }
</style>
