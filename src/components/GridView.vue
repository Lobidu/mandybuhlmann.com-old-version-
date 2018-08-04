<template>
    <div id="grid-view">
        <full-screen-view :image="fullScreenImage" :isActive="fullScreenView" @close="fullScreenView=false"></full-screen-view>
        <div class="tilt"></div>
        <div class="grid">
            <div class="first-row">
                <div class="grid-item first grid-title title">
                    <h2>Interface<br/>Design</h2>
                </div>
                <div class="grid-item  grid-text first title">
                    <p>User Experience<br/>Interface Design<br/>Web Interfaces</p>
                </div>
                <div class="grid-item second" @click="fullScreenView=true; fullScreenImage=images[0]">
                    <image-component
                            :image="images[0]"
                            :shadow="true" />
                </div>
            </div>
            <div class="second-row">
                <div class="grid-item first" @click="fullScreenView=true; fullScreenImage=images[1]">
                    <image-component
                            :image="images[1]"
                            :shadow="true" />
                </div>
                <div class="grid-item second" @click="fullScreenView=true; fullScreenImage=images[2]">
                    <image-component
                            :image="images[2]"
                            :shadow="true" />
                </div>
                <div class="grid-item third" @click="fullScreenView=true; fullScreenImage=images[3]">
                    <image-component
                            :image="images[3]"
                            :shadow="true" />
                </div>
            </div>
        </div>
    </div>

</template>

<script>
    import ImageComponent from './Atoms/Image';
    import FullScreenView from "./Atoms/FullScreenView";
    export default {
        name: "GridView",
        components: {
            FullScreenView,
            ImageComponent
        },
        data() {
            return {
                fullScreenView: false,
                fullScreenImage: null,
                images: [
                    require('../assets/2.png'),
                    require('../assets/1.jpg'),
                    require('../assets/3.jpg'),
                    require('../assets/IMG_20170115_115308.jpg')
                ]
            }
        }
    }
</script>

<style>
    #grid-view {
        margin-top: 0vw;
        margin-bottom: 26vw;
        height: 35vw;
        border: 1px solid #dddddd; /*avoid collapsing margins*/
    }
    #grid-view .tilt {
        background: #dddddd;
        height: 127vw;
        width: 271vw;
        -webkit-transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateX(-60vw) translateY(-33vw);
        transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateX(-60vw) translateY(0);
        -webkit-transform-origin: top left;
        transform-origin: top left;
        position: absolute;
        z-index: 0;
        margin-top: -36vw;
        /* -webkit-box-shadow: 0 10px 30px rgba(0,0,0,0.2); */
        /* box-shadow: 0 10px 30px rgba(0,0,0,0.2); */
    }
    .grid-title h2{
        color: #444444;
        margin: 0;
        font-size: 10.5vw;
        text-align: right;
    }
    .grid-text p {
        color: #444444;
        margin: 0;
        font-size: 4vw !important;
        line-height: 1.5em;
        text-align: left;
    }
    .grid-title.grid-item {
        width: 35vw;
    }
    .grid {
        margin-top: -30vw;
        width: 100vw;
        transform: rotateX(60deg) rotateZ(35deg) translateX(40vw);
        transform-origin: top left;
     }
    .first-row .first.grid-item {
        margin-left: -5vw;
    }
    .first-row {
        align-items: center;

        margin-left: -20vw;
    }
    .second-row {
        margin-left: 12vw;
    }
    .first-row, .second-row {
        display: flex;
        flex-direction: row;
    }
    .grid-item {
        display: inline-block;
        position: relative;
        margin: 2.5vw;
    }
    .grid-item.grid-title {
        margin-right: 12vw;
    }
    .first-row .second.grid-item img, .first-row .second.grid-item{
        height: 35vw;
    }
    .second-row .first.grid-item img, .second-row .first.grid-item {
        height: 60vw;
    }
     .second-row .second.grid-item img, .second-row .second.grid-item{
         height: 40vw;
     }
     .second-row .third.grid-item img, .second-row .third.grid-item{
         height: 40vw;
     }
</style>