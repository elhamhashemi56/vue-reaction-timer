<template>
  <div class="block" v-if="showBox" >Click Me</div>
</template>

<script>
export default {
  props:["delayProps"],
  data(){
    return{
      showBox:false
    }
    
  },
  
  mounted(){
    console.log("component mounted");
    setTimeout(()=>{
      this.showBox=true
    },this.delayProps)
  },

  updated(){
    console.log("component updated");
  },

  unmounted(){
    console.log("component unmounted");
  },
  
  methods:{
    
  }

}
</script>

<style>
.block {
    border: 1px solid rgb(111 151 237);
    padding: 7rem;
    margin: 5rem 30rem;
    background-color: rgb(111 151 237);
    border-radius: 10px;
    text-align: center;
    color: white;
}
</style>