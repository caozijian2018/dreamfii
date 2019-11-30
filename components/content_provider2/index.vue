<template>
    <div class="content_provider">
        <div class="display_flex flex_align_center">
            <div class="flex_1 position_relative">
                <img
                    src="../../static/img/3.jpg"
                    class="width_100 scale1_10 transform_duration2"
                    alt
                />
                <img
                    src="../../static/img/3.jpg"
                    class="content_absolute_img width_50 transform_duration1 position_absolute"
                    :class="{top_50px: _topOrDown}"
                    alt
                />
                <div :class="{top_30px: _topOrDown}" class="display_flex transform_duration1  position_absolute text_position flex_align_center">
                    <div class="border margin_right_20"></div>
                    <span class="font_weight_800 font_size_6">CONTENT PROVIDER</span>
                </div>
            </div>
            <div class="flex_1 padding_left_10p line_height_25px ">
                <div class="width_30 margin_auto">
                    <div class="red">
                        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repudiandae
                        exercitationem voluptate accusantium
                    </div>
                    <div class="margin_top_20 gray_1">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam enim
                        unde obcaecati. voluptates dolorem pariatur velit debitis fugiat enim!
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
        }
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
}
</style>
