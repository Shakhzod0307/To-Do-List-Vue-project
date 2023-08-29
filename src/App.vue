


<template>

  
  <div class="container">
    <div class="box">
    <Header @toggle-add-task="toggleAddTask" :ShowAddTask="ShowAddTask" title="To Do List"/>
    <div v-if="ShowAddTask">
      <AddTask @add-task="addTask"/>
    </div> 
    <Tasks @delete-task="deleteTask" :tasks="tasks"/>

  </div>
  </div>
  

</template>




<script>
import Header from './components/Header.vue';
import Tasks from './components/Tasks.vue';
import AddTask from './components/AddTask.vue';
export default{
  name: "App",
  components:{
    Header,
    Tasks,
    AddTask,
 

  },

  data(){
    return{
      tasks : [],
      ShowAddTask: false
    }
  },
  methods:{
    toggleAddTask(){
      this.ShowAddTask = !this.ShowAddTask
    },
    addTask(task){
      this.tasks = [...this.tasks, task]
    },

    deleteTask(id){
      if(confirm("Are you sure you want to delete?")){
        this.tasks = this.tasks.filter((task)=>task.id !==id)
      }
    }
  },
  created(){
    this.tasks = [
    {
      id : 1,
      text : 'Lorem ipsum dolor',
      day: ' 1 January 1970',
      reminder: false,
    },
    {
      id : 2,
      text : 'Lorem ipsum dolor',
      day: ' 15 January 1980',
      reminder: true,
    },
    {
      id : 3,
      text : 'Lorem ipsum dolor',
      day: ' 28 March 2003',
      reminder: true,
    },
  ]
    
  }

}
</script>

<style scoped>

.container{
  background-color: antiquewhite;
  max-width: 540px;
  display: flex;
  align-items: center;
  text-align: center;
  justify-content: center;
  margin-top: 20px;
  
  border: 1px solid   steelblue;
  padding-bottom: 200px;
  padding-top: 20px;
  border-radius: 15px;
}
.box{
  width: 520px;
}
</style>
