<template>
    <div id="grid-view">
        <div class="grid-title title">
            <h2>User Experience Design</h2>
        </div>
        <div class="grid">
            <div class="first-row grid-item">
                <image-component
                        :image="require('../assets/IMG_20170323_093045(1).jpg')"
                        :shadow="true" />
            </div>
            <div class="second-row">
                <div class="grid-item first">
                    <image-component
                            :image="require('../assets/IMG_20170126_141451.jpg')"
                            :shadow="true" />
                </div>
                <div class="grid-item second">
                    <image-component
                            :image="require('../assets/IMG_20170323_130213(1).jpg')"
                            :shadow="true" />
                </div>
                <div class="grid-item third">
                    <image-component
                            :image="require('../assets/IMG_20170323_130222(1).jpg')"
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
        padding-top: 15vw;
    }
    .grid-title{
        padding: 5vw 7vw;
        position: absolute;
        z-index: 1;
    }
    .grid {
        width: 100vw;
        height:100vh;
        transform: rotateX(60deg) rotateZ(35deg) translateX(40vw);
        transform-origin: top left;
     }
    .first-row.grid-item {
        margin-left: 18vw;
    }
    .second-row {
        display: flex;
        flex-direction: row;
    }
    .grid-item {
        position: relative;
        margin: 2.5vw;
    }
    .first-row .grid-item img, .first-row .grid-item{
        height: 30vw;
    }
    .second-row .first.grid-item img, .second-row .first.grid-item {
        height: 60vw;
    }
     .second-row .second.grid-item img, .second-row .second.grid-item{
         height: 50vw;
     }
     .second-row .third.grid-item {
         margin-top: 10vw;
     }
     .second-row .third.grid-item img, .second-row .third.grid-item{
         height: 35vw;
     }
</style>