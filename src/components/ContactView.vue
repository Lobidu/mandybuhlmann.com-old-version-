<template>
    <div id="contact-view">
        <div class="tilt light"></div>
        <div class="tilt dark"></div>
        <div class="content">
            <div class="title">
                <h2>Like what you see?<br/>Get in touch!</h2>
                <p><a href="mailto:design@mandybuhlmann.com">design@mandybuhlmann.com</a>
                </p>
            </div>
            <div class="mandy">
                <img :src="image"/>
            </div>
        </div>
    </div>
</template>

<script>
  export default {
    name: "ContactView",
    data() {
      return {
        image: require('../assets/Portrait_final.png')
      }
    }
  }
</script>

<style scoped>
    #contact-view {
        max-height: 100vw;
        overflow: hidden;
        position: relative;
        margin-top: -14vw;
    }
    .title h2, .title p{
        margin: 0;
    }
    .title p{
        margin-top: 4.5vw;
    }
    .title{
        width: 90vw;
        padding: 0 5vw 5vw;
        max-width: calc(400px * 3);
    }
    #contact-view .tilt{
        height: 150vw;
        width: 271vw;
        -webkit-transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateX(-60vw) translateY(-33vw);
        transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateX(-60vw) translateY(0);
        -webkit-transform-origin: top left;
        transform-origin: top left;
        position: absolute;
        z-index: 1;
    }
    .light {
        background: #cccccc;
    }
    .dark {
        margin-top: 15vw;
        background: #888888;
    }
    .content {
        display: flex;
        position: relative;
        flex-direction: row;
        z-index: 2;
        padding-top: 47vw;
    }
    .content div.title {
        position: absolute;
        left:0;
        display: block;
    }
    .content div.mandy {
        margin-left: 54%;
        display: block;
    }
    .mandy img{
        width: 50vw;
        display: block;
    }
</style>