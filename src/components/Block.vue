<template>
  <div class="block_Container">
    <div class="block" v-if="showBox" @click="stopTimer" >Click Me</div>
  </div>
 
</template>

<script>
export default {
  props:["delayProps"],
  data(){
    return{
      showBox:false,
      reactionTimer:0,
      timer:null
    }
    
  },
  
  mounted(){
    console.log("component mounted");
    setTimeout(()=>{
      this.showBox=true
      this.startTimer()
    },this.delayProps)
  },

  updated(){
    console.log("component updated");
  },

  unmounted(){
    console.log("component unmounted");
  },
  
  methods:{
    startTimer(){
      this.timer = setInterval(() => {
        this.reactionTimer += 10
      }, 10);
     
    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit("end",this.reactionTimer)
      console.log(this.reactionTimer);
    }
  }

}
</script>

<style>
.block {
    border: 1px solid rgb(111 151 237);
    margin-top: 1rem;
    width: 15rem;
    height: 12rem;
    background-color: rgb(77 120 151);
    border-radius: 10px;
    text-align: center;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
}
.block_Container{
  display: flex;
  justify-content: center;
  
}
</style>