<template>
    <div class="container">
        <div class="element">
            <div class="content">
                <div class="title">
                    <h2>Posters</h2>
                    <p>
                        Under the motto "See it all" I created several landscape-themed posters.
                       This selection displays four of the most promising ones.</p>
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
    .swipe-view .swipecontainer img{
        height: 60vw;
        max-height: 80vh;
    }
</style>