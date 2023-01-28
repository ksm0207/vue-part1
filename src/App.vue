<template>
  <RoomDetail v-if="this.isOpen"
           :rooms = "this.rooms"
           :useIndex = "this.useIndex"
           @modalClose="modalClose" />
  <!-- Rooms -->
  <Rooms :rooms="this.rooms"
         @modalOpen="modalOpen"/>
</template>

<script>

import roomData from './assets/part1/data/rooms.js';
import Rooms from './components/Rooms.vue'
import RoomDetail from './components/RoomDetail.vue'


export default {
  name: 'App',
  data () {
    return {
      isOpen : false,
      useIndex : null,
      rooms : roomData
    }
  },

  methods : {
    modalOpen : function ($event){
      console.log("Modal Open : ", $event)
      if($event != null || $event != undefined) {
        this.useIndex = $event
      }
      window.scrollTo({ top: 0, behavior: "smooth" });
      return this.isOpen = !this.isOpen
    },
    modalClose: function ($event) {
      console.log("Modal Close", $event)
      return this.isOpen = $event
    },
  },

  components: {
    Rooms,
    RoomDetail
  },

  updated () {
    console.log("Isopen : ", this.isOpen)
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
