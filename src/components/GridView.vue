<template>
    <div id="grid-view">
        <div class="tilt"></div>
        <div class="grid">
            <div class="first-row">
                <div class="grid-item first grid-title title">
                    <h2>Interface<br/> Design</h2>
                </div>
                <div class="grid-item second">
                    <image-component
                            :image="require('../assets/2.png')"
                            :shadow="true" />
                </div>
            </div>
            <div class="second-row">
                <div class="grid-item first">
                    <image-component
                            :image="require('../assets/1.jpg')"
                            :shadow="true" />
                </div>
                <div class="grid-item second">
                    <image-component
                            :image="require('../assets/3.jpg')"
                            :shadow="true" />
                </div>
                <div class="grid-item third">
                    <image-component
                            :image="require('../assets/4.jpg')"
                            :shadow="true" />
                </div>
            </div>
        </div>
    </div>

</template>

<script>
    import ImageComponent from './Atoms/Image';
    export default {
        name: "GridView",
        components: {
            ImageComponent
        }
    }
</script>

<style>
    #grid-view {
        background: #dddddd;
        margin-top: 0vw;
        height: 55vw;
        border: 1px solid #dddddd; /*avoid collapsing margins*/
    }
    #grid-view .tilt {
        background: #dddddd;
        height: 130vh;
        width: 200vw;
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
        color: #ffffff;
        margin: 0;
        font-size: 10.5vw;
        text-align: right;
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