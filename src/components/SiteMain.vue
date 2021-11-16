<template>
     <div id="site_main">
          
          
          <Card_song />     
     
          
     </div>
     
</template>

<script>
import Card_song from "./CardSong.vue"


export default {
     components:{
          
          Card_song,
     },
}
</script>

<style scoped lang="scss">
#site_main{
     background-color: #1e2d3b;
     height: 100vh;
}




</style>
