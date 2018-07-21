<template>
    <main>
        <tile-view/>
        <swipe-view/>
        <mask-view/>
        <portfolio-view/>
    </main>
</template>

<script>
    import TileView from './components/TileView.vue'
    import SwipeView from './components/SwipeView.vue'
    import GridView from './components/GridView.vue'
    import MaskView from "./components/MaskView";
    import PortfolioView from "./components/PortfolioView";

    export default {
        name: "App",
        components:{
            PortfolioView,
            MaskView,
            TileView,
            SwipeView,
            GridView
        }
    }
</script>

<style>
    @import "assets/MyFontsWebfontsKit.css";
    html {
        box-sizing: border-box;
    }
    body {
        margin:0;
        background-color: #00807f;
    }
    *, *:before, *:after {
        box-sizing: inherit;
    }
    main {
        font-family: NTF-Grand-Regular, Arial, sans-serif;
        font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #444444;
        overflow: hidden;
    }
    h1, h2, h3, h4, h5, h6 {
        font-weight: normal;
        text-transform: uppercase;
    }
    h2 {
        color: #ffffff;
        margin: 0;
        font-size: 8vw;
    }
    p {
        color: #ffffff;
        font-size: 4vw;
        max-width: 60vw;
    }
    .title p {
        font-size: 5vw;
    }
    @media screen and (min-width: 600px){
        h2 {
            font-size: 7vw;
        }
        p, .title p {
            font-size: 4vw;
        }
    }
    @media screen and (min-width: 900px){
        h2 {
            font-size: 6vw;
        }
        p, .title p {
            font-size: 2vw;
        }
    }
    @media screen and (min-width: 1500px){
        h2 {
            font-size: 4vw;
        }
        p, .title p{
            font-size: 1.5vw;
            max-width: 40vw;
        }
    }
</style>