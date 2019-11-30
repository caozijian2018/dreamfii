<template>
    <div class="banner position_relative">
        <div class="hoverdiv hover1" style="">
        </div>
        <div class="width_65 pcs display_flex white flex_align_center">
            <div class="flex_1">
                <h1>Dreamfii -------</h1>
                <div class="font_size_40 font_weight_800 margin_top_20">
                    CREATING
                    <br />DIGITAL BUSINESS
                </div>
                <div class="head_button margin_top_3">Contact Us</div>
            </div>
            <div class="flex_1 display_flex flex_jusify_space">
                <div class="width_50 left_phone position_relative overflow_hidden">
                    <div class="position_absolute phone_hover_box width_100 height_97 overflow_hidden">
                        <img src="../../static/img/secret.png" class="width_92 display_block margin_auto" alt="">
                    </div>
                    <img src="../../static/img/banner-iphone.png" class="width_100 z_index100 position_relative" alt="">
                </div>
                <div class="width_50 left_phone position_relative overflow_hidden margin_left_20">
                    <div class="position_absolute phone_hover_box scroll_animate_box width_100 height_97 overflow_hidden">
                        <img src="../../static/img/taichi.gif" class="width_92 display_block margin_auto" alt="">
                    </div>
                    <img src="../../static/img/banner-iphone.png" class="width_100 z_index100 position_relative" alt="">
                </div>
                <!-- <div class="width_50">
                    <img src="../../static/img/banner-iphone.png" class="width_100" alt="">
                </div> -->
                <!-- <img src=".././../static/img/3.jpg" class="width_100" alt /> -->
            </div>
        </div>
    </div>
</template>

<script>
export default {
    mounted(){
        this.scrollTop();
    },
    methods:{
        scrollTop(){
            setInterval(() => {
                var distance = Math.random()*2000 + 300;
                this.$jquery(".scroll_animate_box").animate({ scrollTop: distance}, 3000);
            }, 3000);
        }
    }
};
</script>
<style lang="less">
@keyframes scroll {
    from {
        margin-top: 0;
    }
    100% {
        margin-top: -700%;
    }
}


@keyframes changecolor{
    from {
        // background: red;
        opacity: 0;
    }
    100% {
        // background: blue;

        opacity: 1;
    }
}
.phone_hover_box{
    border-radius: 50px;

    filter: drop-shadow(0px 14px 28px rgba(0,0,0,-0.7));
}
.hover1{

    background: linear-gradient(120deg,  #43e97b 0%, #d4fc71 100%);
    animation-name: changecolor;
    animation-duration: 2s;
    animation-timing-function: linear;
    /*Chrome & Safari*/
    -webkit-animation-name: changecolor;
    -webkit-animation-duration: 2s;
    -webkit-animation-timing-function: linear;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-direction: alternate;
}
.banner {
    .scroll_animate_box img{
    //    animation-duration: 4s;
    //     animation-name: scroll;
    //     animation-timing-function: linear;
    //     -webkit-animation-name: scroll;
    //     -webkit-animation-duration: 4s;
    //     -webkit-animation-timing-function: linear;
    //     -webkit-animation-iteration-count: infinite;
    //     -webkit-animation-direction: alternate;
    }
    .left_phone {
        // background-image: url("../../static/img/taichi.gif");
        // background-size: 93% 94%;
        // background-position: 10px 17px;
        // background-repeat:no-repeat;
        // box-shadow: 20px 20px 20px rgba(200, 200, 200, 0.6)
    }
    height: 750px;
    background: linear-gradient(120deg, #d4fc71 0%, #43e97b 100%);
    // background-image: url("../../static/img/back/banner-img.gif");
    transition-duration: 1s;
    
}
</style>
