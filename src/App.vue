<template id="app">
  <h1>Pixel Art</h1>

  <Grid :colors="currentPalette"/>
  <Palette @change-palette="changePalette"/>
</template>

<script>
import Grid from './components/Grid.vue';
import Palette from './components/Palette.vue';

export default {
  name : 'App',

  components: {
    Grid,
    Palette,
  },

  data(){
    return {
      currentPalette:["#f94144","#f3722c","#f8961e","#f9c74f","#90be6d","#43aa8b","#4d908e","#577590"],
    }
  },

  methods : {
    changePalette(palette){
      this.currentPalette = palette;
      // console.log(this.currentPalette)
    }
  }
}

</script>

<style >
  #app {
    display:block;
    margin:0 auto;
    text-align: center;
  }

</style>
