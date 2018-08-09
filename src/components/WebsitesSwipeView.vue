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
                  require("../assets/cc4.png"),
                  require("../assets/cc3.png"),
                  require("../assets/cc5.png"),
                  require("../assets/cc1.png"),
                  //require("../assets/cc6.jpg"),
                 // require("../assets/cc2.jpg"),
                    require("../assets/cc7.png"),
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
        margin-top: 12vw;
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