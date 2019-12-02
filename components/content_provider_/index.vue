<template>
    <div class="content_provider2">
        <div class="display_flex flex_align_center phone_block phone_width_90 phone_margin">
            <div class="flex_1 padding_left_10p phone_padding_left_0 display_flex flex_end line_height_25px phone_block">
                <div class="width_50 margin_top_40 margin_auto phone_width_100 font_size_14">
                    <div class="red">
                        {{text2}}
                    </div>
                    <div class="margin_top_20 gray_1">
                        {{text3}}
                    </div>
                </div>
            </div>
            <div class="flex_1 position_relative phone_margin_top_60px">
                <img
                    :src="img1"
                    class="width_100 scale1_10 transform_duration2"
                    alt
                />
                <img
                    :src="img2"
                    :class="{bos_shadow1: text2 !='Taichi-lifestyle Video Portal' }"
                    class="content_absolute_img width_70 transform_duration1 position_absolute"
                    :style="{transform: 'translateY('+ topDownDistance/15+'px)'}"
                    alt
                />
                <div :style="{transform: 'translateY('+ topDownDistance/13+'px)'}" class="phone_none transform_duration1 display_flex position_absolute text_position flex_align_center">
                    <span class="font_weight_800 font_size_34 gray_2">{{text1}}</span>
                    <div class="border margin_left_20"></div>
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
    computed:{
       _topOrDown(){
           return this.topOrDown
       } 
    },
     
};
</script>
<style lang="less" >
@keyframes scroll {
    from {
        transform: translateY(30px)
    }
    100% {
        transform: translateY(-30px)
    }
}
.content_provider2 {
    .text_position {
        left: -47%;
        top: 10%;
        .border {
            width: 50px;
            border: 1px solid #000;
        }
    }

    .content_absolute_img {
        left: -15%;
        // box-shadow:-6px 6px 8px rgba(200, 200, 200, 0.3);
        top: 25%;
        // animation-name:scroll;
		// animation-duration:5s;
		// animation-timing-function:linear;
		// 		/*Chrome & Safari*/
		// -webkit-animation-name:scroll;
		// -webkit-animation-duration:5s;
		// -webkit-animation-timing-function:linear;
		// -webkit-animation-iteration-count:infinite;
		// -webkit-animation-direction:alternate;
    }
    @media screen and (max-width: 800px){
        .content_absolute_img{
            left: 25%;
            top: -20%;
        }
    }
}
</style>
