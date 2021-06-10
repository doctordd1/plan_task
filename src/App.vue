<template>
  <div id="app">

    <TimeTable :tasks_real.sync="tasks"></TimeTable>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TimeTable from './components/TimeTable.vue'

export default {
  name: 'App',
  data:function(){
    return {
      test:'test',
      last_id:3,
      tasks:[
        {id:1,title:"Название задачи"},
        {id:2,title:"Название задачи 2"},
        {id:3,title:"Название задачи 23"},
      ]
    }
  },
  methods:{
    add:function(){
     this.tasks.push({
       id:0,
       title:""
     })
    },
    getIDTask:function(newTask){
      console.log(newTask)
      if(newTask.title.length != 0){
        newTask.id = this.last_id + 1;
        this.last_id ++;
      }
    }
  },


  components: {
    TimeTable
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
</style>
