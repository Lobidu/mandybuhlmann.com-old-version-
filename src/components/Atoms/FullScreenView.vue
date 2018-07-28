<template>
    <div class="full-screen-view" @click="$emit('close')" :class="{'active':isActive}">
        <img :src="image"/>
    </div>
</template>

<script>
    export default {
        name: "FullScreenView",
        props: {
            image: {
                type: String,
                default: null
            },
            isActive: {
                type: Boolean,
                default: false
            }
        }
    }
</script>

<style scoped>
    .full-screen-view.active{
        top:0;
        z-index: 999;
        background-color: rgba(255,255,255,0.5);
    }
    .full-screen-view {
        position: fixed;
        z-index: -1;
        height:100vh;
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
        transition: all 500ms;
    }
    .full-screen-view img{
        height: 0;
        opacity: 0;
        transition: all 200ms;
    }
    .full-screen-view.active img{
        height:60%;
        max-height: 60%;
        opacity: 1;
        box-shadow: 10px 10px 50px 20px rgba(0,0,0,0.2);
    }
</style>