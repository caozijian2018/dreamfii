<template>
    <div class="container display_flex flex_column" :style="{height:height_}">
        <!-- <video-head></video-head> -->
        <!-- <div class="width_100 head_com display_flex position_absolute" :class="{'top_50px': $store.state.scroll_top > 50 && $store.state.scroll_top < 150, 'notop':$store.state.scroll_top > 10}" style="z-index: 1000">
            {{$store.state.scroll_top}}
            <div class="display_flex flex_jusify_space flex_align_center width_80 margin_auto">
                <img v-if="$store.state.scroll_top > 10"  src="../../static/img/loog2.png" style="width:200px;" alt="">
                <img v-else src="../../static/img/loog1.png" style="width:200px;" alt="">
                <div class="display_flex black right_text" :style="{color: $store.state.scroll_top < 10 ? 'white' : 'black'}">
                    <div class="t1 margin_left_14 font_size_20">
                        home
                    </div>
                    <div class="t1 margin_left_14 font_size_20">
                        about
                    </div>
                    <div class="t1 margin_left_14 font_size_20">
                        Contact Us
                    </div>
                </div>
            </div>
        </div> -->
        <div
            v-loading.fullscreen.lock="fullscreenLoading"
            class="flex_1 overflow_scroll scroll_box"
            style
        >
            <!-- <login-box v-if="show_login" @close="show_login=false"></login-box> -->
            <nuxt-child :is-scroll-bottom="is_scroll_bottom"></nuxt-child>
        </div>
    </div>
</template>

<script>
import isScrollBottom from "../../util/is_scroll_bottom";
import bus from "../../util/bus";
import isPc from "../../util/get_pc_or_phone";
import videoHead from "../../components/videoHead";


export default {
    components: {
        videoHead
    },
    data() {
        return {
            prev_scroll: 0,
            height_: "",
            show_login: false,
            is_scroll_bottom: false,
            fullscreenLoading: false
        };
    },
    mounted() {
        this.setHeightAndISPc();
        this.watchOnresize();
    },
    methods: {
         pc_phone() {
            this.$store.state.is_pc = isPc();
        },
        watchOnresize() {
            window.onresize = this.setHeightAndISPc;
        },
        setHeightAndISPc() {
            this.height_ = innerHeight + "px";
            this.$store.state.innerHeight = this.height_;
            this.pc_phone();
        }
    }
};
</script>

<style lang='less'>
</style>