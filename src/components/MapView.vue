<template>
    <div id="map-view">
        <div class="constraint" :class="{'fullview':fullView}"  @click="fullView = !fullView">
            <div>
                <div class="tilt-nomove">
                    <div class="paper paper-left"></div>
                    <div class="paper paper-right message">
                    </div>
                    <div class="paper paper-right-top">
                    </div>
                </div>
            </div>
        </div>
        <div class="map-container" :class="{'fullview':fullView}" @click="fullView = !fullView">
            <div class="actionable map-shadow">
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
    }
    .map-container {
        height:45vw;
        overflow: visible;
    }
     .map-container img{
         width:100%;
     }
     .position {
         margin-left: 50vw;
         position: absolute;
         overflow: visible;
         z-index: 9;
     }
     .tilt {
         transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateY(0);
         transform-origin: bottom left;
         overflow: visible;
         position: relative;
     }
    .actionable {
        position: relative;
        transition: transform 200ms ease-in-out;
    }
    .actionable:hover {
        transform: translateY(-0.8vw);
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
        box-shadow: 1vw 0.5vw 1.2vw rgba(0,0,0,0.2);
    }
    .actionable:hover .lower-layer {
        box-shadow: 1vw 1.5vw 3vw rgba(0,0,0,0.2);
    }
    .middle-layer {
        z-index: 3;
        margin-left:8vw;
        margin-top:-3vw;
        background-position: 50% 0;
        box-shadow: 1vw 0.8vw 1.2vw rgba(0,0,0,0.2);
    }
    .actionable:hover .middle-layer {
        box-shadow: 1vw 1.8vw 3vw rgba(0,0,0,0.2);
    }
    .upper-layer {
        z-index: 5;
        margin-left:16vw;
        margin-top:-6vw;
        background-position: 100% 0;
        box-shadow: 1vw 1.5vw 1.2vw rgba(0,0,0,0.2);
    }
    .actionable:hover .upper-layer {
        box-shadow: 1vw 2.3vw 3vw rgba(0,0,0,0.2);
    }
    .position, .tilt, .map-layer, .in-between-layer{
        transition: box-shadow 200ms ease-in-out, all 1s ease-in-out;
    }
    .fullview .actionable {
        transform: none;
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
        width: 100vw;
        overflow-x: hidden;
    }
    .tilt-nomove {
        margin-top: -14vw;
        position: absolute;
        transform-origin: top left;
        transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg);
    }
    .paper {
        position: absolute;
        background: #f7f2ed;
        width: 44vw;
        height: 57vw;
        box-shadow: 3px 3px 3px rgba(0,0,0,0.2);
    }
    .message {
        padding: 2vw;
        font-size: 7vw;
    }
    .paper-right {
        left: 105vw;
        top: -2vw;
        transform: rotate(10deg);
    }
    .paper-right-top {
        background: #ffffff;
        left: 105vw;
        top: -11vw;
        transform: rotate(-5deg);
    }
    .paper-left {
        left: 44vw;
    }
</style>