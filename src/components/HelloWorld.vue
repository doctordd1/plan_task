<template>
  <div class="hello">
    {{ props }}
    <input v-model="props">
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data:function(){
      return {
          props:this.msg
      }
  },
  watch:{
      props:function(val){
          this.$emit("update:msg",val)
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

