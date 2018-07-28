<template>
    <div id="portfolio">
        <div class="content">
            <div class="title">
                <h2>Fine Arts</h2>
                <p>Besides being digitally creative, I have continously been pursuing Fine Arts.
                This selection showcases a variety of techinques and materials used over the past couple of years.
                </p>
            </div>
            <div class="swipe-view">
                <div class="swipecontainer">
                    <div v-for="(image, index) in images" class="art-display">
                        <img :src="image.image" :key="index"/>
                        <span class="art-description"><b>{{image.date}}</b> - {{image.description}}</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "PortfolioView",
        data(){
            return {
                images:[
                    {
                        image: require("../assets/2a761d_4c2f148c9a384291a4b2d72bafc65432.jpg"),
                        title: "Untitled",
                        date: "2011",
                        description: "Paper and Pencil"
                    },
                    {
                        image: require("../assets/Maus.jpg"),
                        title: "Mouse",
                        date: "2017",
                        description: "Polymer Clay, Acrylic Paint"
                    },
                    {
                        image: require("../assets/IMG_20170220_163457.jpg"),
                        title: "Baby",
                        date: "2017",
                        description: "Paper and Pencil"
                    },
                    {
                        image: require("../assets/2a761d_cbb9ef84cc674f31aa0ad447d2621e19.jpg"),
                        title: "Street Art",
                        date: "2015",
                        description: "Mixed Material on Cardboard"
                    },
                    {
                        image: require("../assets/Portrait.jpg"),
                        title: "Tube People",
                        date: "2014",
                        description: "Digital Drawing"
                    },
                    {
                        image: require("../assets/2a761d_0130f5f9ed0346fe87e277e34434b57e.jpg"),
                        title: "Living in a Box",
                        date: "2015",
                        description: "Paper, Acrylic Glass, Plastic, Metal"
                    },
                    {
                        image: require("../assets/2a761d_6f503058b74e4b6fba9f353656437816.jpg"),
                        title: "Self Portrait",
                        date: "2009",
                        description: "Oil on Canvas"
                    },
                    {
                        image: require("../assets/2a761d_62e0f0dbd5be4b4abe81007d6105b57c.jpg"),
                        title: "Untitled",
                        date: "2015",
                        description: "Analog Photography"
                    },
                    {
                        image: require("../assets/Candle_drips.png"),
                        title: "Untitled",
                        date: "2018",
                        description: "Vector Mesh"
                    }
                ]
            }
        }
    }
</script>

<style scoped>
     #portfolio {
         position: relative;
         width:100vw;
     }
    .tilt {
        height: 130vh;
        width: 200vw;
        transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateX(-60vw) translateY(-33vw);
        transform-origin: top left;
        position: absolute;
        z-index: 1;
        box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    }
    .content {
        padding: 1px; /*Avoid collapsing margins*/
        /*margin-top: 15vw;*/
        z-index: 2;
        position: relative;
    }
    .content .title {
        /*margin-top: -16vw;*/
    }
     .title{
         padding: 1px; /*Avoid collapsing margins*/
         color: #cccccc;
         padding: 5vw 5vw;
     }
     .title h1, .title p {
         margin: 0
     }
     .container {
         overflow: hidden;
     }
     .swipe-view .swipecontainer img{
         height: 60vw;
         max-height: 50vh;
     }
    .art-display .art-description{
        color: #cccccc;
        opacity: 0;
        transition: opacity 1s ease-in-out;
    }
    .art-display:hover .art-description{
        opacity: 1;
    }
</style>