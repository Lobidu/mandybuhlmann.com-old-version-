<template>
    <div class="container">
        <div class="element">
            <div class="content">
                <div class="title">
                    <h2>See it all</h2>
                    <p>
                        Under the motto "See It All" these posters are part of a larger travel-themed series.</p>
                </div>
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
                    require("../assets/Mountains.png"),
                    require("../assets/Poles.png"),
                    require("../assets/Desert.png"),
                    require("../assets/Oceans.png"),
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
        margin-top: 3vw;
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