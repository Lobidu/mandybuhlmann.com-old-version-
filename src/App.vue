<template>
    <div class="no-overflow">
        <main :class="scrollClass">
            <div class="background-green push-down">
                <tile-view @toggleScrolling="toggleScrolling"/>
                <map-view/>
                <swipe-view/>
                <logo-view/>
            </div>
            <div class="background-green">

                <grid-view/>
                <portfolio-view/>
            </div>
        </main>
    </div>

</template>

<script>
    import TileView from './components/TileView.vue'
    import SwipeView from './components/SwipeView.vue'
    import GridView from './components/GridView.vue'
    import MaskView from "./components/MaskView";
    import PortfolioView from "./components/PortfolioView";
    import MapView from "./components/MapView";
    import LogoView from "./components/LogoView";

    export default {
        name: "App",
        components:{
            LogoView,
            MapView,
            PortfolioView,
            MaskView,
            TileView,
            SwipeView,
            GridView
        },
        data(){
          return {
              scrollClass: 'scroll'
          }
        },
        methods: {
            toggleScrolling(shouldBodyScroll){
                if(shouldBodyScroll){
                    this.scrollClass = 'scroll'
                }
                else {
                    this.scrollClass = 'no-scroll'
                }
            }
        }
    }
</script>

<style>
    @import "assets/MyFontsWebfontsKit.css";
    html {
        box-sizing: border-box;
    }
    ::-webkit-scrollbar {
        width: 0px;  /* remove scrollbar space */
        background: transparent;  /* optional: just make scrollbar invisible */
    }
    body {
        margin:0;
        background: #dddddd;
    }
    *, *:before, *:after {
        box-sizing: inherit;
    }
    main {
        font-family: NTF-Grand-Regular, Arial, sans-serif;
        font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #444444;
        width:100vw;
        overflow-x: hidden;
        position: relative;
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
            max-width: 40vw;
        }
    }
    .push-down {
        padding-bottom: 40vw;
    }
    .background-green {
        background-color: #00807f;
    }
    .background-dark-grey {
        background-color: #888888;
    }
    .swipe-view{
        overflow-y: scroll;
    }
    .swipe-view .swipecontainer {
        display: flex;
        padding: 0 5vw;
        width: 100vw;
        overflow-x: scroll;
        overflow-y: visible;
        margin-bottom: 15vw;
    }
    .swipe-view .swipecontainer>* {
        margin-right: 5vw;
    }
    .swipe-view .swipecontainer img{
        display: inline-block;
        box-shadow: 0 1vw 2vw rgba(0,0,0,0.2);
    }
    .swipe-view .swipecontainer>*:last-of-type{
        margin-right: 0px;
        padding-right: 30px;
    }
</style>