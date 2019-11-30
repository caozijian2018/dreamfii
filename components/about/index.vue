<template>
    <div class="aboutdreamfii">
        <div class="display_flex width_65 margin_auto flex_jusify_space flex_align_center phone_width_90 phone_margin_top_60px phone_block">
            <div class="width_45 phone_width_100">
                <!-- border -->
                <div class="border scale1_10 transform_duration1"></div>
                <div
                    class="font_size_40 margin_top_4 transilateX-1 transform_duration2"
                >ABOUT DREAMFII</div>
                <div class="margin_top_3 gray_1 line_height_25px transilateX2 transform_duration2">
                    At Dreamfii, our mission goes beyond just producing digital mobile
                    content and bringing beautiful experience to users. Our job also
                    includes providing advertising solutions to your products as efficient
                    and effective as possible. Your products and our products need to
                    convert successfully. Our ultimate mission to to make that happen.
                </div>
            </div>
            <div class="width_45 phone_width_100 phone_margin_top_60px">
                <img src="../../static/img/back/about.jpg" class="width_100" alt />
            </div>
        </div>
    </div>
</template>

<script>
export default {};
</script>
<style lang="less">
.aboutdreamfii {
    margin: 100px 0;
    .border {
        width: 100px;
        height: 2px;
        background: orangered;
    }
    @media screen and (max-width: 800px){
        margin-top: 250px;
    }
}
</style>
