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
     }
   },
   created(){
     this.tasks= [
     {
       id:1,
       text:'Doctors Appointment',
       day:'March 1st at 2.30pm',
       reminder:true,
     },
     {
       id:2,
       text:'Meeting at School',
       day:'March 3rd at 1.30pm',
       reminder:true,
     },
     {
       id:3,
       text:'Food Shoping',
       day:'March 14th at 1.30pm',
       reminder:false,
     }
     ]
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
