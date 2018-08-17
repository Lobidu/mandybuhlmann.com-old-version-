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
                  require("../assets/Campcrater_Home2-01.png"),
                  require("../assets/Campcrater_Home-04.png"),
                  require("../assets/Campcrater_Home-02.png"),
                  require("../assets/Campcrater_Home-05.png"),
                  require("../assets/Campcrater_Home-03.png"),
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