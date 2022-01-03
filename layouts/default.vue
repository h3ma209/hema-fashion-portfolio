<template>
  <div>
    <loader></loader>
    <cursor-follower></cursor-follower>
    <Nuxt />
  </div>
</template>

<script>
import CursorFollower from '../components/CursorFollower.vue'
import Loader from "../components/Loader.vue"
export default {
  
  components:{
    CursorFollower,
    Loader,
  },
  setup() {
    
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;700&display=swap');
html {
  cursor: none;
  font-family: 'Poppins', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
  
  
/* 
  color: #212a4d !important;
  background: wheat; */
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

</style>
