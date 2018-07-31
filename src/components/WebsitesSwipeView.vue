<template>
    <div class="container">
        <div class="element">
            <div class="content">
                <div class="swipe-view">
                    <div class="swipecontainer">
                        <div v-for="(image, index) in images" :key="index">
                            <img :src="image"/>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        name: "SwipeView",
        data(){
            return {
                images:[
                    require("../assets/Mockup1.jpg"),
                    require("../assets/Mockup2.jpg"),
                    require("../assets/Mockup5.jpg"),
                    require("../assets/Mockup4.jpg"),
                ]
            }
        }
    }
</script>

<style scoped>
    .title{
        color: #cccccc;
        padding: 5vw;
    }
    .title h1, .title p {
        margin: 0
    }
    .container {
        margin-top: 10vw;
        overflow: hidden;
    }
    .swipe-view .swipecontainer {
        height: 70vw;
        max-height: 90vh;
    }
    .swipe-view .swipecontainer img{
        height: 60vw;
        max-height: 80vh;
    }
</style>