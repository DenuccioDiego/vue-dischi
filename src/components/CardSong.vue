<template>
     
     <div>
          
          <div class="row justify-content-center gutter-cards m-0 pt-5">
               <div class="col-2 card text-center" v-for="song in songs" :key="song.author">
                    <img :src="song.poster" class="card-img-top" :alt="song.author">
                    <div class="card-body color_card">
                         <h5 class="card-title">{{song.title}}</h5>
                         
                         <p class="card-text">
                              <small class="text-muted">{{song.author}}</small><br>
                              <small class="text-muted">{{song.year}}</small>
                         </p>
                    </div>
               </div>
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

.color_card{
     background-color: #2e3a46;

}

.card{
     
     border:none;
     background-clip: content-box;
     background-color: transparent;
}

.card-img-top{
     border-top-left-radius:0;
     border-top-right-radius: 0;
}

.gutter-cards{
     --bs-gutter-x: 4rem;
     --bs-gutter-y: 2rem;
}

.card-title{
     color:white;
}
</style>
