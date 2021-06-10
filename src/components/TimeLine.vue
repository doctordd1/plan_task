<template>
    <tr >
        <td>{{task_real.id}}</td>
        <td><input type="text" v-model="task_real.title"></td>
    </tr>

</template>

<script>
export default {
    name: "TimeLine",
    props:{
        task:{
            title:"",
            time: "",
            completed: "",
            id:"0"
        }
    },
    data:function(){
        return {
            task_real:this.task
        }
    },
  watch:{
    task_real:{
      handler:function(newTask){
          if(newTask.id == 0){
              this.$parent.getIDTask(newTask)
          }
        //   console.log(newTask);
        //   console.log(oldTask);
      },
      deep:true
    }
  },
}
</script>

<style scroped>

</style>