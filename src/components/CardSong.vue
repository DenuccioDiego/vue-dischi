<template>
     
     <div class="row">
          <div class="col-2" v-for="song in songs" :key="song.author">
              <img :src="song.poster"
              class="img-fluid"

               /> 
          </div>

     </div>

</template>

<script>
import axios from "axios"

export default{

     data(){
          return{
               songs : []
          }
     },

    mounted(){
    axios
    .get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(r=>{
      console.log(r.data.response);
      
      this.songs = r.data.response

    }).catch(e=>{
      console.log(e,"Ops")
    })
  }
}
</script>

<style scoped lang="scss">

</style>
