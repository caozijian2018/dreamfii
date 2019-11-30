<template>
    <div
        class="banner position_relative display_flex flex_align_center flex_center"
        :style="{
      height: $store.state.is_pc ? '700px' : $store.state.innerHeight + 'px'
    }"
    >
        <div class="hoverdiv hover1" style></div>
        <img src="../../static/img/back/banner-img.png" class="pcs width_30 left80" alt />
        <div
            class="width_65 display_flex white flex_align_center phone_block position_relative z_index10000"
            style
        >
            <div class="flex_1">
                <h1>Dreamfii -------</h1>
                <div class="font_size_40 font_weight_800 margin_top_20">
                    CREATING
                    <br />DIGITAL BUSINESS
                </div>
                <div class="head_button margin_top_3" @click="tobottom()">Contact Us</div>
            </div>
            <div class="flex_1 display_flex flex_jusify_space phone_none">
                <div class="width_50 position_relative overflow_hidden">
                    <div
                        class="position_absolute phone_hover_box width_100 height_97 overflow_hidden"
                    >
                        <img
                            src="../../static/img/secret.png"
                            class="width_92 display_block margin_auto"
                            alt
                        />
                    </div>
                    <img
                        src="../../static/img/banner-iphone.png"
                        class="width_100 z_index100 position_relative"
                        alt
                    />
                </div>
                <div class="width_50 position_relative overflow_hidden margin_left_20">
                    <div
                        class="position_absolute phone_hover_box phone_border_radius scroll_animate_box width_100 height_97 overflow_hidden"
                    >
                        <img
                            src="../../static/img/taichi.gif"
                            class="width_92 display_block margin_auto"
                            alt
                        />
                    </div>
                    <img
                        src="../../static/img/banner-iphone.png"
                        class="width_100 z_index100 position_relative"
                        alt
                    />
                </div>
            </div>
        </div>
        <div
            class="width_50 display_none phone_position phone_block position_relative overflow_hidden"
        >
            <div
                class="position_absolute phone_hover_box phone_border_radius scroll_animate_box width_100 height_97 overflow_hidden"
            >
                <img
                    src="../../static/img/taichi.gif"
                    class="width_92 display_block margin_auto"
                    alt
                />
            </div>
            <img
                src="../../static/img/banner-iphone.png"
                class="width_100 z_index100 position_relative"
                alt
            />
        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        this.scrollTop();
    },
    methods: {
        tobottom(){
           this.$emit("tobottom")
        },
        scrollTop() {
            setInterval(() => {
                var distance = Math.random() * 2000;
                this.$jquery(".scroll_animate_box").animate(
                    { scrollTop: distance },
                    2000
                );
            }, 2000);
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

@keyframes changecolor {
    from {
        // background: red;
        opacity: 0;
    }
    100% {
        // background: blue;

        opacity: 1;
    }
}
.phone_hover_box {
    border-radius: 50px;
    // filter: drop-shadow(0px 14px 28px rgba(0,0,0,-0.7));
}
.hover1 {
    background: linear-gradient(120deg, #43e97b 0%, #d4fc71 100%);
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
    .scroll_animate_box img {
        //    animation-duration: 4s;
        //     animation-name: scroll;
        //     animation-timing-function: linear;
        //     -webkit-animation-name: scroll;
        //     -webkit-animation-duration: 4s;
        //     -webkit-animation-timing-function: linear;
        //     -webkit-animation-iteration-count: infinite;
        //     -webkit-animation-direction: alternate;
    }
    height: 750px;
    background: linear-gradient(120deg, #f9d423 0%, #ff4e50 100%);
    // background: linear-gradient(120deg, #d4fc71 0%, #43e97b 100%);
    // background-image: url("../../static/img/back/banner-img.gif");
    transition-duration: 1s;
    @media screen and (max-width: 800px) {
        .phone_border_radius {
            border-radius: 27px;
        }
        .phone_position {
            position: absolute;
            left: 50%;
            bottom: -55%;
            z-index: 1002;
            transition: 0.4s;
            transform: translate(-50%, -50%);
        }
    }
}
</style>
