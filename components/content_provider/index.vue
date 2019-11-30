<template>
    <div class="content_provider">
        <div class="display_flex flex_align_center phone_block phone_width_90 phone_margin">
            <div class="flex_1 position_relative phone_width_100">
                <img
                    :src="img1"
                    class="width_100  scale1_10 transform_duration2"
                    alt
                />
                <img
                    :src="img2"
                    class="content_absolute_img width_50 transform_duration1 position_absolute"
                    :class="{top_50px: _topOrDown}"
                    alt
                />
                <div :class="{top_30px: _topOrDown}" class="display_flex phone_none transform_duration1  position_absolute text_position flex_align_center">
                    <div class="border margin_right_20"></div>
                    <span class="font_weight_800 font_size_6">{{text1}}</span>
                </div>
            </div>
            <div class="flex_1 phone_margin_top_60px padding_left_10p phone_padding_left_0 line_height_25px phone_width_100 phone_width_100">
                <div class="width_30 margin_auto phone_width_100">
                    <div class="red">
                        {{text2}}
                    </div>
                    <div class="margin_top_20 gray_1 phone_width_100">
                        {{text3}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        topOrDown:{
            type: Boolean
        },
        img1:{

        },
        img2: {

        },
        text1:{
            type: String,
            default: ""
        },
        text2:{
            type: String,
            default: ""
        },
        text3:{
            type: String,
            default: ""
        },
    },
    computed:{
       _topOrDown(){
           return this.topOrDown
       } 
    },
     
};
</script>
<style lang="less">
@keyframes scroll {
    from {
        transform: translateY(30px)
    }
    100% {
        transform: translateY(-30px)
    }
}
.content_provider {
    .text_position {
        right: -25%;
        top: 10%;
        .border {
            width: 50px;
            border: 1px solid #000;
        }
    }

    .content_absolute_img {
        right: -15%;
        box-shadow:6px 6px 8px rgba(200, 200, 200, 0.3);
        top: 25%;
    }

    @media screen and (max-width: 800px){
       .content_absolute_img {
            top: 75%;
            box-shadow:6px 6px 8px rgba(200, 200, 200, 0.3);
            left: 25%;
        } 
    }

}
</style>
