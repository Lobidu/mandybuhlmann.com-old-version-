<template>
    <div class="container">
        <div class="element">
            <div class="content">
                <div class="title">
                    <h2>Logo Design</h2>
                    <p>The quick brown fox jumps over the lazy dog. The very quick brown fox jumps over the very lazy dog.</p>
                </div>
                <div id="swipe-view">
                    <div class="swipecontainer">
                        <img v-for="(image, index) in images" :src="image" :key="index"/>
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
                    require("../assets/Comet-01_1.png"),
                    require("../assets/Comet-01_2.png"),
                    require("../assets/Comet-02_1.png"),
                    require("../assets/Comet-02_2.png"),
                    require("../assets/Comet-03_1.png"),
                    require("../assets/Comet-03_2.png"),
                ]
            }
        }
    }
</script>

<style scoped>
    #swipe-view{
        overflow-y: scroll;
    }
    #swipe-view .swipecontainer {
        display: flex;
        padding: 30px;
        width: 100vw;
        overflow-y: scroll;
        margin-bottom: 15vw;
    }
    #swipe-view .swipecontainer img {
        display: inline-block;
        height: 60vw;
        max-height: 50vh;
        margin-right: 30px;
        box-shadow: 10px 10px 20px rgba(0,0,0,0.2);
    }
    #swipe-view .swipecontainer img:last-of-type{
        margin-right: 0px;
    }
    .title{
        color: #cccccc;
        padding: 5vw 30px;
    }
    .title h1, .title p {
        margin: 0
    }
    .container {
        overflow: hidden;
    }
</style>