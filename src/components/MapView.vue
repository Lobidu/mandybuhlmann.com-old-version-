<template>
    <div>
        <div id="map-view" :class="{'fullview':fullView}" @click="fullView = !fullView">
            <div class="map position">
                <div class="tilt">
                    <div class="map-layer lower-layer">
                        <div class="in-between-layer"></div>
                    </div>
                    <div class="map-layer middle-layer">
                        <div class="in-between-layer"></div>
                    </div>
                    <div class="map-layer upper-layer"></div>
                </div>
            </div>
        </div>
        <div class="constraint" :class="{'fullview':fullView}"  @click="fullView = !fullView">
            <div>
                <div class="next-background">
                    <div class="arrow arrow-left"></div>
                    <div class="arrow arrow-right"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "MapView",
        data() {
            return {
                fullView: false
            }
        }
    }
</script>

<style scoped>
    #map-view {
        width:100vw;
        overflow: hidden;
        height:45vw;
    }
     #map-view img{
         width:100%;
     }
     .position {
         margin-left: 50vw;
         position: absolute;
         z-index: 9;
     }
     .tilt {
         transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateY(0);
         transform-origin: bottom left;
     }
    .map .map-layer, .map .in-between-layer {
    }
    .map .in-between-layer {
        width: 12vw;
        position: absolute;
        top: 0;
        height: 100%;
        right: 0;
        transform: skewY(14deg);
        transform-origin: bottom right;
        background: #ffffff;
        z-index: 55;
    }
    .map .map-layer {
        position: absolute;
        height: 56.25vw;
        width:20vw;
        background-size: cover;
    }
    @media screen and (min-width: 960px) {
        .map .map-layer {
            background-image: url("../assets/map2.png");
        }
    }
    @media screen and (max-width: 960px) {
        .map .map-layer {
            background-image: url("../assets/map_960.png");
        }
    }
    @media screen and (max-width: 500px) {
        .map .map-layer {
            background-image: url("../assets/map_500.png");
        }
    }
    .lower-layer {
        z-index: 1;
        background-position: 0 0;
        box-shadow: 0 10px 15px rgba(0,0,0,0.2);
    }
    .middle-layer {
        z-index: 3;
        margin-left:8vw;
        margin-top:-3vw;
        background-position: 50% 0;
        box-shadow: 0 11px 12px rgba(0,0,0,0.2);
    }
    .upper-layer {
        z-index: 5;
        margin-left:16vw;
        margin-top:-6vw;
        background-position: 100% 0;
        box-shadow: 0 15px 19px rgba(0,0,0,0.2);
    }
    .position, .tilt, .map-layer, .in-between-layer{
        transition: all 1s ;
    }
    .fullview .position{
        margin-left:5vw;
        margin-top: -10vw;
    }
    .fullview .tilt{
        transform:none;
    }
    .fullview .map .in-between-layer {
        transform: skewY(0);
        width: 0;
    }
    .fullview .map-layer {
        margin: 0;
        width: 30vw;
        display: inline-flex;
        box-shadow: none;
    }
    .fullview .map-layer.middle-layer {
        margin-left: 30vw;
    }
    .fullview .map-layer.upper-layer {
        margin-left: 60vw;
    }
    .constraint{
        width:100vw;
        overflow-x: hidden;
        margin-top: -28vw;
        margin-bottom: 13vw;
    }
    .next-background {
        position: absolute;
        background: #dddddd;
        transform-origin: top left;
        height: 130vh;
        width: 200vw;
        transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateX(-60vw) translateY(-33vw);
    }
    .arrow {
        position: absolute;
        background: #ffffff;
        width: 11vw;
        height: 10vw;
        top: -5vw;
        transition: all 1000ms;
    }
    .arrow-right {
        left: 62%;
        clip-path: polygon(0% 0%,0% 100%,100% 50%);
    }
    .arrow-left {
        left: 32%;
        clip-path: polygon(100% 100%,100% 0%,0% 50%);
    }
    .fullview .arrow-left {
       transform: translateX(-100vw);
    }
    .fullview .arrow-right {
        transform: translateX(100vw);
    }

</style>