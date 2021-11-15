<template>
     <div>
          <div v-if="!loading" id="card-song" class="row justify-content-center gutter-cards m-0 pt-5">
               <div class="col-2 card text-center " v-for="song in songs" :key="song.author">
                    
                    <div class="card-body color_card p-4">
                         <img :src="song.poster" class="card-img-top" :alt="song.author">
                         <h3 class="card-title py-3">{{song.title}}</h3>
                         
                         <p class="card-text">
                              <small class="text-muted">{{song.author}}</small><br>
                              <small class="text-muted">{{song.year}}</small>
                         </p>
                    </div>
               </div>
          </div> 

          <div class="loading" v-else>
               <span>loading...</span>
          </div>

     </div>
             

</template>

<script>
import axios from "axios"

export default{

     data(){
          return{
               songs : [],
               loading : true,
               error : "",
          };
     },

     mounted(){
          setTimeout(this.callApi, 5000);
     },
   
     methods: {
          callApi(){
               axios
               .get("https://flynn.boolean.careers/exercises/api/array/music")
               .then(r=>{
                    console.log(r.data.response);
                    this.songs = r.data.response;
                    this.loading = false;

               }).catch(e=>{
                    console.log(e,"Ops");
                    this.error = "Ops ${e}";
               })
          }
     }
}
</script>

<style scoped lang="scss">
small{
     font-weight: 500;
}

h3{
     font-weight: 700;

}
.color_card{
     background-color: #2e3a46;
}

.card{
     
     border:none;
     background-clip: content-box;
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

.loading{
     color: white;
     font-size: 8rem;
     text-align: center;
}
</style>
