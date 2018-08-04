<template>
    <div class="image" :class="{'thickness':shadow,'hover': hover}">
        <img v-if="image" :src="image"/>
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
            shadow: {
                type: Boolean,
                default: true
            },
            hover: {
                type: Boolean,
                default: true
            }
        },
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
        /*box-shadow: 1px 1px #eee, 2px 2px #eee, 3px 3px #eee, 4px 4px #eee;*/
    }
    @media screen and (max-width: 700px){
        .thickness.image img, .thickness.image .fill{
            /*box-shadow: 1px 1px #eee, 2px 2px #eee;*/
        }
    }
    .image {
        height: 100%;
        margin: 0;
    }
    .image img{
        transition: all 200ms ease-in-out;
        box-shadow: 0.5vw 0.5vw 1.5vw rgba(0,0,0,0.2);
    }
    .image.hover:hover img{
        transform: translateY(-1vw) translateX(-1vw);
        box-shadow: 1.5vw 1.5vw 2vw -0.2vw rgba(0,0,0,0.2);
    }
    .fill {
        width: 34vw;
    }

</style>