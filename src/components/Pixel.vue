<template>
    <div class="pixel" @click="increaseCounter" v-bind:style="{ backgroundColor : colors[counter]}">

    </div>
</template>

<script>
    export default {
        name : "pixel",

        props:['colors'],

        data(){
            return {
                counter:0,
            }
        },
        
        methods : {
            increaseCounter(){
                if(this.counter< this.colors.length-1){
                    this.counter++;
                } else {
                    this.counter=0;
                }
            }
        }
    }

</script>