<template>
     <div id="site_main">
          <div class="container_cards">
     
               <Card_song />     
     
          </div>
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
     
}




</style>
