<template>


    <!-- <HelloWorld :msg.sync="test"/> -->
    <table >
      <thead>
        <tr>
          <th>ID</th>
          <th>Title</th>
        </tr>
      </thead>
        <button @click="add">Add a component</button>
    
        <TimeLine  v-for="(task, index) in tasks" :key="index" :task.sync="tasks[index]" ></TimeLine>

   
    </table>

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TimeLine from './TimeLine.vue'

export default {
  name: 'TimeTable',
  props:['tasks_real'],

  data:function(){
    return {
      test:'test',
      last_id:3,
      tasks:this.tasks_real
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
    TimeLine
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
