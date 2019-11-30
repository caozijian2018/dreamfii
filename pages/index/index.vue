<template>
    <div class="container display_flex flex_column" :style="{height:$store.state.innerHeight+'px'}">
        <!-- <video-head @showLogin="showLogin" class :class="{height0:is_scroll_bottom}"></video-head> -->
        <div
            v-loading.fullscreen.lock="fullscreenLoading"
            class="flex_1 overflow_scroll scroll_box"
            style
        >
            <!-- <login-box v-if="show_login" @close="show_login=false"></login-box> -->
            <nuxt-child></nuxt-child>
        </div>
    </div>
</template>

<script>
import bus from "../../util/bus";
import isPc from "../../util/get_pc_or_phone";


export default {
    components: {
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
     
    },
    methods: {
    }
};
</script>

<style lang='less'>
</style>