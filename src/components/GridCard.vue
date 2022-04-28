<template>
    <div class="col">
        <div class="card">
            <img :src="imgsrc" class="card-img-top" alt="..." id="card_img">
            <div class="card-body">
                <h5 class="card-title">{{obj.title}}</h5>
                <p class="card-text">{{obj.overview}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'GridCard',
  props: {
      obj: {

      }
  },
  data(){
    return{
        imgsrc: "https://image.tmdb.org/t/p/w500"+this.obj.poster_path,
    }
  },
  
}
</script>

<style scoped>
#card_img{
    width: 40%;
    margin: auto;
}
</style>