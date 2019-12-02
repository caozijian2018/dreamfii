<template>
    <div class="width_90 margin_auto display_flex flex_jusify_space wrop">
        <div class="width_15 margin_bottom_15 text_center" v-for="item in arr" :key="item">
            <img :src="item" class="width_50 phone_width_100" alt="">
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            arr:[
                require("../../static/img/partener/logo01.gif"),
                require("../../static/img/partener/logo02.gif"),
                require("../../static/img/partener/logo03.gif"),
                require("../../static/img/partener/logo04.gif"),
                require("../../static/img/partener/logo05.gif"),
                require("../../static/img/partener/logo06.gif"),
                require("../../static/img/partener/logo07.gif"),
                require("../../static/img/partener/logo08.gif"),
                require("../../static/img/partener/logo09.gif"),
                require("../../static/img/partener/logo10.gif"),
                require("../../static/img/partener/logo11.gif"),
                require("../../static/img/partener/logo12.gif")
            ]
        }

    }
}

</script>
<style lang='less'>
</style>