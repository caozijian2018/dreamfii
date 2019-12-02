<template>
    <div class="content_provider">
        <div class="display_flex flex_align_center phone_block phone_width_90 phone_margin">
            <div class="flex_1 position_relative phone_width_100">
                <img
                    :src="img1"
                    class="width_100  scale1_10 scale_origin_left transform_duration1"
                    alt
                />
                <img
                    :src="img2"
                    class="content_absolute_img width_70 bos_shadow1 opacity0 transform_duration7 position_absolute"
                    :style="{transform: 'translateY('+ topDownDistance/13+'px)'}"
                    
                    alt
                />
                <div :style="{transform: 'translateY('+ topDownDistance/15+'px)'}" class="display_flex phone_none transform_duration7  position_absolute text_position flex_align_center">
                    <div class="border margin_right_20"></div>
                    <span class="font_weight_800 font_size_34 gray_2">{{text1}}</span>
                </div>
            </div>
            <div class="flex_1 phone_margin_top_60px padding_left_10p phone_padding_left_0 line_height_25px phone_width_100 phone_width_100">
                <div class="width_50 margin_top_40 margin_auto  phone_width_100 font_size_14">
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
        topDownDistance:{
            type: Number,
            default:0
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

@keyframes show_little_img {
    from {
        opacity: 0;
    }
    70%{
        opacity: 40%;
    }
    100% {
        opacity: 100%;
    }
}
.content_provider {
    .show_little_img{
        animation-name: show_little_img;
        animation-duration: 2s;
        animation-timing-function: linear;
        /*Chrome & Safari*/
        -webkit-animation-name: show_little_img;
        -webkit-animation-duration: 2s;
        -webkit-animation-timing-function: linear;
    }
    .text_position {
        right: -64%;
        top: 10%;
        .border {
            width: 80px;
            border: 1px solid #000;
        }
    }

    .content_absolute_img {
        right: -15%;
        // box-shadow:6px 6px 8px rgba(200, 200, 200, 0.3);
        top: 28%;
    }

    @media screen and (max-width: 800px){
       .content_absolute_img {
            top: 70%;
            box-shadow:6px 6px 8px rgba(200, 200, 200, 0.3);
            left: 25%;
        } 
    }

}
</style>
