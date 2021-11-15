<template>
  <div id="app">
    <div class="row">
      <div class="col-xs|sm|md|lg|xl-1-12">
        <div class="card">
          <div class="card-body">
            <h3 class="card-title">Title</h3>
            <p class="card-text">Text</p>
          </div>
        </div>
      </div>
      <div class="col-xs|sm|md|lg|xl-1-12">
        <div class="card">
          <div class="card-body">
            <h3 class="card-title">Title</h3>
            <p class="card-text">Text</p>
          </div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import axios from "axios"

export default {
  name:"App",
  components: {
    
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
