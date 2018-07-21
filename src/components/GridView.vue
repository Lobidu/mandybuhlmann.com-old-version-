<template>
    <div class="grid">
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
        <div class="grid-item">
            <div class="fill" style="background-color:#fff;"></div>
            <span class="drop-shadow"></span>
        </div>
    </div>
</template>

<script>
    import ImageComponent from './TileViewComponents/Image';
    export default {
        name: "GridView",
        components: {
            ImageComponent
        }
    }
</script>

<style scoped>
 .grid {
     display: flex;
     justify-content: center;
     width: 100%;
     flex-wrap: wrap;
 }
    .grid-item{
        position: relative;
        padding: 2vw;
        opacity: 0.7;
    }
    .drop-shadow {
        background-color: rgba(3,3,3,0.1);
        width: 25vw;
        height: 99vw;
        position: absolute;
        transform-origin: 0 0;
        transform: skewX(-60deg) rotateY(0deg) rotateZ(0);
    }
  .fill {
     height: 25vw;
      width: 25vw;
     display: block;
 }
</style>