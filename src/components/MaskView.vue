<template>
    <div id="mask-view">
        <div class="image-mask">
        </div>
        <div class="other-half">
            <div class="content">
                <h2>UX Design</h2>
                <p>The job requires extra pluck and zeal from every young wage earner. Jaded zombies acted quaintly but kept driving their oxen forward.</p>
                <p>A mad boxer shot a quick, gloved jab to the jaw of his dizzy opponent.</p>
            </div>
            <div class="showcase">
                <img src="../assets/IMG_20170323_130213(1).jpg"/>
                <img src="../assets/IMG_20170323_130222(1).jpg"/>
                <img src="../assets/IMG_20170323_093045(1).jpg"/>
                <img src="../assets/IMG2_20170228_151926.jpg"/>
                <img src="../assets/2a761d_a4eca78ebcdb45dc9f0f48aac6777d39.jpg"/>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "MaskView"
    }
</script>

<style scoped>
    #mask-view{
        background-color: #888888;
        position: relative;
        color: #ffffff;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items: flex-start;
    }
    .image-mask{
        height:100vh;
        width:50vw;
        background-image: url("../assets/IMG_20170126_141451.jpg");
        background-position: 50% 50%;
        background-size: cover;
        background-repeat: no-repeat;
        z-index: 1;
        box-shadow: 10px 10px 30px rgba(0,0,0,0.2);
    }

    .other-half{
        width: 50vw;
    }
    @media screen and (max-width: 960px){
        .image-mask {
            width:100vw;
            height:50vh;
        }
        .other-half {
            width: 100vw;
        }
    }
    .content {
        padding: 5vw 7vw;
    }
    .showcase {
        height: 40vh;
        display: flex;
        overflow-y: scroll;
        padding: 2vw;
        box-sizing: border-box;
        width:100%;
        z-index:0;
    }
    .showcase img {
        height: 100%;
        margin-right: 2vw;
        box-shadow: -5px 5px 10px rgba(0,0,0,0.2);
    }
</style>