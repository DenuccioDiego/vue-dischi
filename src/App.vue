<template>
  <div id="app">

    <SiteHeader />
    <SiteMain />


     
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader.vue"
import SiteMain from "./components/SiteMain.vue"
import axios from "axios"


export default {
  name:"App",
  components: {
    SiteHeader,
    SiteMain,
  },
  mounted(){
    axios
    .get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(r=>{
      console.log(r);
    }).catch(e=>{
      console.log(e,"Ops")
    })
  }
}
</script>

<style lang="scss">

@import "../node_modules/bootstrap/scss/bootstrap.scss";

body {
  font-family: "Montserrat"; 
}


</style>
