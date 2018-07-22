<template>
  <div id="app">
      <div class="full-screen-view" @click="fullScreenView=null" :class="{'active':fullScreenView}">
          <img :src="fullScreenImage"/>
      </div>
      <div class="stage" :class="{'blur':fullScreenView}">
          <div class="position-relative">
              <div class="tilt background"></div>
          </div>
          <div class="tilt">
              <div class="row" v-for="(row, rowIndex) in rows" :key="rowIndex"
              :style="'width:'+calculateWidth(rowIndex)+'vw; margin-left: '+ calculateMargin(rowIndex) +'vw;'"
              >
                  <div class="ItemCard title-item" v-if="rowIndex==1">
                      <title-component class="tile object" text="MANDY<br/>BUHLMANN"/>
                  </div>

                  <div class="ItemCard" v-for="(image, imageIndex) in row"
                       :key="imageIndex" @click="fullScreenImage = image.image; fullScreenView=image.image">
                      <image-component
                              :text="image.text"
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

export default {
  name: 'app',
  components: {
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
              [
                  {
                      image: require("../assets/Envelope-01.svg")
                  }
              ],
              [
                  {
                      image: require("../assets/Ice_Cream.png")
                  },
                  {
                      image: require("../assets/Comet.svg")
                  }
              ],
              [
                  {
                      image: require("../assets/UX.svg")
                  },
                  {
                      image: require("../assets/Bumblebee.png")
                  },
                  {
                      image: require("../assets/Pencil.svg")
                  },
              ],

              [
                  {
                      color: '#ff8ded',
                      image: require("../assets/Triangles.svg")
                  },
                  {
                      image: require("../assets/Peel.svg")
                  },
                  {
                      color: '#ff9463'
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
                return 80
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
        padding-top: 10vw;
        width: 100vw;
        margin-bottom: -60vw;
        overflow: hidden;
    }
    .position-relative{
        position: relative;
    }
    .background {
        width: 260vw;
        height: 160vw;
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
    .full-screen-view.active{
        z-index: 999;
        background-color: rgba(255,255,255,0.5);
    }
    .full-screen-view {
        position: fixed;
        z-index: -1;
        height:100vh;
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
        transition: all 500ms;
    }
    .full-screen-view img{
        height: 0;
        opacity: 0;
        transition: all 200ms;
    }
    .full-screen-view.active img{
        height:60%;
        max-height: 60%;
        opacity: 1;
        box-shadow: 10px 10px 50px 20px rgba(0,0,0,0.2);
    }
    .ItemCard{
        margin: 3vw;
        position: relative;
    }
</style>
