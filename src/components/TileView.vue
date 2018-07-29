<template>
  <div id="app">
      <full-screen-view :image="fullScreenImage" :isActive="fullScreenView" @close="fullScreenView=false"></full-screen-view>
      <div class="stage">
          <div class="position-relative">
              <div class="tilt background"></div>
          </div>
          <div class="tilt">
              <div class="row" v-for="(row, rowIndex) in rows" :key="rowIndex"
              :style="'width:'+calculateWidth(rowIndex)+'vw; margin-left: '+ calculateMargin(rowIndex) +'vw;'"
              >
                  <div class="ItemCard title-item" v-if="rowIndex===0">
                      <image-component
                              :image="require('../assets/envelope_zu.png')"
                              :shadow="true"
                              :hover="false"
                              class="tile object oversize"/>
                  </div>

                  <div class="ItemCard title-item" v-if="rowIndex===1">
                      <title-component class="tile object" text="MANDY<br/>BUHLMANN"/>
                  </div>

                  <div class="ItemCard" v-for="(image, imageIndex) in row"
                       :key="imageIndex" @click="fullScreenImage = image.image; fullScreenView=image.image">
                      <image-component
                              :color="image.color"
                              :image="image.image"
                              :shadow="image.shadow"
                              class="tile object"/>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import TitleComponent from './Atoms/Title.vue'
import ImageComponent from './Atoms/Image.vue'
import MapView from "./MapView";
import FullScreenView from "./Atoms/FullScreenView";

export default {
  name: 'app',
  components: {
      FullScreenView,
      MapView,
    TitleComponent,
    ImageComponent
  },
    watch:{
      fullScreenView(isFullScreen){
          if(isFullScreen){
              this.$emit('toggleScrolling', false)
          }
          else {
              this.$emit('toggleScrolling', true)
          }
      }
    },
  data(){
      return {
          fullScreenImage: null,
          fullScreenView: null,
          rows: [
              [],
              [
                  {
                      image: require("../assets/Ice_Cream.jpg")
                  },
                  {
                      image: require("../assets/Comet.png")
                  }
              ],
              [
                  {
                      image: require("../assets/UX.png")
                  },
                  {
                      image: require("../assets/Bumblebee.jpg")
                  },
                  {
                      image: require("../assets/Pencil.png")
                  },
              ],
              [
                  {
                      image: require("../assets/Triangles.png")
                  },
                  {
                      image: require("../assets/Supermandy (2).png")
                  },
                  {
                    image: require("../assets/cup_coffee.png")
                  },
              ]
          ]
      }
  },
    methods:{
        calculateMargin(rowIndex){
            if(rowIndex<1){
                return 0
            }
            else {
                // return Math.ceil(38.99 * rowIndex) - 80 // when image height 50vw
                 return Math.ceil(22 * rowIndex) - 40
            }
        },
        calculateWidth(rowIndex){
            if (rowIndex<1){
                return 100
            }
            else {
                return 130
            }
        }
    }
}
</script>

<style>
    .stage {
        padding-top: 5vw;
        width: 100vw;
        margin-bottom: -65vw;
    }
    .position-relative{
        position: relative;
    }
    .background {
        width: 288vw;
        height: 235vw;
        position: absolute;
        background: #dddddd;
        top: -25vw;
        left: -25vw;
    }
    .tilt {
        transform: rotateX(60deg) rotateY(0deg) rotateZ(35deg) translateY(-60vw);
        transform-origin: top left;
    }
    .row {
        display: flex;
        justify-content:flex-end;
        flex-direction: row;
        flex-wrap:wrap;
        transform-style: preserve-3d;
    }

    .ItemCard{
        margin: 3vw;
        position: relative;
    }
</style>
