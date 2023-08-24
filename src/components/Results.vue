<template>
  <p>Reaction Time: {{ scoreProps }} ms</p>
  <h2 class="rank">{{ rank }}</h2>
  
</template>

<script>
export default {
props:["scoreProps"],
data(){
    return{
        rank:null
    }
    
},
mounted(){
    if(this.scoreProps < 250 ){
        this.rank= "Sehr gut"

    }else if(this.scoreProps < 400){
        this.rank= "Gut"

    }else{
        this.rank= "Nicht gut"
    }
}
}
</script>

<style>
.rank {
    font-size: 1.4em;
    color: #0faf78;
    font-weight: bold;
}
</style>