<template>
    <div id="palette" @click="changePalette">
        <div id="colorCircle"></div>
        <p v-bind:style="{color : currentPalette[zero]}">{{ paletteName }}</p>
    </div>
</template>

<script>
    export default {
        name : "palette",

        data(){

            return {
                palettes:{
                    basic : ["grey","#f94144","#f3722c","#f8961e","#f9c74f","#90be6d","#43aa8b","#4d908e","#577590"],
                    forest : ['grey','#002b00','#4d7436','#00873e','#c0a772',"#e3dac1","#e40010","#80150a","#54030e"],
                    pastel : ["grey","#ffadad","#ffd6a5","fdffb6","#caffbf","#9bf6ff","#a0c4ff","#bdb2ff","#ffc6ff"],
                    modern : ["grey","#00173d","#005f73","#0a9396","#94d2bd","#e9d8a6","#ee9b00","#ca6702","#bb3e03",],
                    bluink : ["grey","#355070","#515575","#6d597a","#915f78","#b56576","#e56b6f","#e88c7d","#eaac8b"],
                    vibrant : ["grey","#ffe9a9","#ffc518","#ff8528","#b52dc8","#6817c5","#3c1596","#2d0983","#210b56"],
                    disco : ["grey","#00f6cc","#a4f603","#f4f503","#f800a4","#f601eb","#dc03f5","#a306f6","#0ba5f6"]
                },
                currentPalette:["grey","#f94144","#f3722c","#f8961e","#f9c74f","#90be6d","#43aa8b","#4d908e","#577590"],
                paletteName:"basic",
                zero:1
            }
        },

        methods:{
            changePalette(){

                console.log(this.currentPalette);

                let foundPalette=false;
                for(let palette in this.palettes){
                    console.log(this.palettes[palette]);

                    
                    if(palette===this.paletteName){
                        foundPalette=true;
                        console.log('heyyy');

                        if(palette==="disco"){
                            this.currentPalette=this.palettes['basic'];
                            this.$emit('change-Palette',this.currentPalette);
                            this.paletteName="basic";
                           
                            return;
                        }
                        
                        continue;
                    }
                    if(foundPalette){
                        this.currentPalette=this.palettes[palette];
                        console.log(this.currentPalette);
                        this.$emit('change-Palette',this.currentPalette);
                        this.paletteName=palette;
                        // console.log(this.currentPalette,this.colorPalette)
                        return;
                    }

                   
                }

        
            },


        }
    }
</script>

<style>
    #palette {
        position: absolute;
        top:45%;
        left:50px;
        height:10%;
    }
    #colorCircle {
        aspect-ratio: 1;
        border-radius: 50%;
        height:100%;
        background-color: v-bind(currentPalette[zero]);
        border:2px solid antiquewhite;
    }

    #palette p {
        padding:3px;
        background-color: grey;
        margin-top:10px;
    }
</style>