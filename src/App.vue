<template>
<div class="container">
  <Header title="Task Tracker"/>
  <Tasks :tasks="tasks" />
  </div>
  </template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'

export default {
   name:'App',
   components:{
     Header,
     Tasks
   },
   data(){
     return{
       tasks:[]
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
