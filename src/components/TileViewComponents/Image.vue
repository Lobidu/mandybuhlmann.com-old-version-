<template>
    <div class="image" :class="{'thickness':shadow}">
        <span class="shadow cover" v-if="shadow"></span>
        <img v-if="image" :src="image" />
        <h1 v-else-if="text" class="text">{{text}}</h1>
        <div v-else class="fill" :style="'background-color:' + color +';'"></div>
    </div>
</template>

<script>
    export default {
        name: "ImageComponent",
        props: {
            color: {
                type: String,
                default: '#cccccc'
            },
            image: {
                type: String
            },
            text: {
                type: String
            },
            shadow: {
                type: Boolean,
                default: true
            }
        },
        data(){
            return {
                fullView: false
            }
        }
    }
</script>

<style scoped>
    .text{
        align-self: end;
    }
    .image img, .image .fill  {
        z-index: 1;
        height: 25vw;
        display: block;
    }
    .thickness.image img, .thickness.image .fill{
        box-shadow: 1px 1px #ddd, 2px 2px #ddd, 3px 3px #ddd, 4px 4px #ddd;
    }
    .image {
        height: 100%;
        margin: 0;
    }
    .image img, .image .shadow{
        transition: all 200ms;
    }
    .image:hover img{
        transform: translateY(-10px) translateX(-10px);
    }
    .image:hover .shadow{
        box-shadow: 10px 10px 40px 10px rgba(0,0,0,0.2);;
    }
    .fill {
        width: 34vw;
    }
    .image .shadow {
        background:  rgba(0,0,0,0.2);;
        position: absolute;
        z-index: -1;
        top: 0;
        left: 0;
        height:100%;
        width:100%;
        display: block;
        box-shadow: 10px 10px 30px 10px rgba(0,0,0,0.2);
    }
</style>