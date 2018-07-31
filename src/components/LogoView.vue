<template>
    <div id="LogoView">
        <div class="title">
            <div>
                <h2>Brand Design</h2>
                <p>
                    Campcrater is an ongoing private project providing a Pay-As-You-Go solution for Campsites.
                    This set of designs was made to explore the company's branding.
                </p>
            </div>
        </div>
        <div class="center">
            <div class="logo-view-container">
                <div v-for="image in images" class="logo">
                    <img :src="image"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "LogoView",
        data(){
            return {
                images:[
                    require("../assets/Comet-01_1_square.png"),
                    require("../assets/Comet-04_sq.png"),
                    require("../assets/Comet-03_2_square.png"),
                    require("../assets/Comet-03_1_square.png"),
                    require("../assets/Comet-02_1_square.png"),
                    require("../assets/Comet-02_2_square.png"),

                ]
            }
        }
    }
</script>

<style scoped>
    .title h2, .title p{
        margin: 0;
    }
    .title{
        width: 90vw;
        padding: 5vw;
        max-width: calc(400px * 3);
    }
    .center {
        display: flex;
        justify-content: center;
    }
    .logo-view-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        max-width: calc(400px * 3);
        box-sizing: border-box;
        margin: -2.5vw 2.5vw 0 2.5vw;
    }
    .logo {
        width:calc(95vw/3);
        max-width: 400px;
        padding: 2.5vw;
    }
    .logo img{
        width: 100%;
        height: auto;
        box-sizing: border-box;
        display: block;
        box-shadow: 0px 1vw 2vw rgba(0,0,0,0.2);
    }
</style>