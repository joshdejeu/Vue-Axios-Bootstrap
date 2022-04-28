<template>
    <div class="smallPic" @click="clock(obj)" @mouseover="hover = true" @mouseleave="hover = false">
        <ticket @adultTicket="adultBought" @childTicket="childBought" v-if="hover"></ticket>
        <img v-bind:src=concact+source id="img">
    </div>
</template>

<script>

export default {
  name: 'MovieCard',
  components: {
  },
  data(){
    return{
    }
  },
  methods:{
  
  }
}
</script>

<style>


</style>
