<template>
    <div class="container">
        <div class="element">
            <div class="content">
                <div class="title">
                    <h2>Logo Design</h2>
                    <p>The quick brown fox jumps over the lazy dog. The very quick brown fox jumps over the very lazy dog.</p>
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