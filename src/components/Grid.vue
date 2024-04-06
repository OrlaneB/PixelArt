<template>
    <div id="grid">
        <Pixel v-for="index in this.widthGrid*this.widthGrid" :key="index" :colors="colors" />
    </div>
</template>

<script>
    import Pixel from './Pixel.vue';

    export default {

        name : 'Grid',

        components: {
            Pixel,
        },

        data() {
            return {
                widthGrid : 6,
                // colors : ["#737372","#F8BBD0","#F06292","#1A237E","#42A5F5","#F48FB1","#AD1457","#000000"]
            }
        },

        props:['colors'],

    }
</script>

<style>
    #grid {
        display: grid;
        grid-template-columns: repeat(v-bind(widthGrid),1fr);
        grid-template-rows: repeat(v-bind(widthGrid),1fr);
        gap:1px;
        width:35%;
        margin : 30px auto;
    }

    .pixel {
        width:100%;
        aspect-ratio: 1;
    }
</style>