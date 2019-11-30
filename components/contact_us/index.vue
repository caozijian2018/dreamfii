<template>
    <div class="display_flex flex_end width_100 workwithusbox">
        <div class="width_90 colorbox display_flex flex_align_center">
            <div class="flex_1">
                <img src="../../static/img/3.jpg" class="width_100 vertical_middle" alt="">
            </div>
            <div class="flex_2 white">
                <div class="width_70 margin_auto">
                    <div class="font_size_36 font_weight_800 position_relative margin_bottom_4">
                        <div class="bord"></div>
                        WANT TO WORK WITH US?
                    </div>
                    <div class="line_height_25px">
                        Let’s do business together. To get started, 
                        all you need to do is click this button. Then our staff will get back to you soon.
                    </div>
                    <div class="head_button margin_top_20">
                        CONTACT US
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {

}

</script>
<style lang='less'>
.workwithusbox{
    .bord{
        width: 70px;
        position: absolute;
        left: -120px;
        top:24px;
        border: 1px solid #fff;
    }
    .colorbox{
        background-image: linear-gradient(30deg, #ff5858 0%, #f09819 100%);
    }
}
</style>