<template>
     <div>
          
          <input v-model="song" @keyup="search(song)" type="text" placeholder="Cerca">

          
          
     </div>


</template>

<script>


export default {
     data(){
          return{
               song : ""
          }
          
     },

    methods:{
          search(song){
              console.log(song)
         }
    }
}
</script>


<style scoped lang="scss">


</style>