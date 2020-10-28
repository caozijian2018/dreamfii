<template>
    <div>
        <div class="display_flex flex_end width_100 contact_with_us scale1_10 transform_duration1_2 scale_origin_right">
            <div class="width_91 colorbox phone_padding_20px phone_width_100 display_flex flex_align_center">
                <div class="flex_1 phone_none">
                    <img src="../../static/img/back/cs.jpg" class="width_100 vertical_middle" alt="">
                </div>
                <div class="flex_2 white">
                    <div class="width_70 margin_auto phone_width_100 ">
                        <div class="font_size_36 font_weight_800 position_relative margin_bottom_4">
                            Contact Us
                        </div>
                        <div v-if="op=='mby'">
                            <div class="line_height_25px font_size_14">
                                Company: Dreamfii HK Limited
                            </div>
                            <div class="line_height_25px font_size_14">
                                Address:  FLAT B5 1/F MANNING IND BUILDING 116-118 HOW MING STREET KWUN TONG KL
                            </div>
                            <div class="font_size_14 font_weight_800 white margin_top_4px">
                                E-Mail: customer@dreamfii.com
                            </div>
                            <div class="font_size_14 font_weight_800 white margin_top_4px">
                                Phone Number: +8617380401211
                            </div>
                            <div class="font_size_14 font_weight_800 white margin_top_4px">
                                Legal form of company: Limited Company 
                            </div>
                            <div class="font_size_14 font_weight_800 white margin_top_4px">
                                CEO: Zuopeng Guo
                            </div>
                            <div class="font_size_14 font_weight_800 white margin_top_4px">
                                Registration Number: 2368793
                            </div>
                            <div class="font_size_14 font_weight_800 white margin_top_4px">
                                VAT Number: 66078972
                            </div>
                            
                            



                            
                        </div>
                        <div v-if="op!='mby'">
                            <div class="line_height_25px font_size_14">
                                Company: 成都雪骋科技有限公司
                            </div>
                            <div class="line_height_25px font_size_14">
                                Address: 成都市武侯区金花桥街道金川路75号附5号
                            </div>
                            <div class="font_size_21 font_weight_800 white margin_top_20">
                                E-Mail: customer@dreamfii.com
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import getOp from "../../util/get_country"
export default {
    data(){
        return {
            op: ""
        }
    },
    mounted(){
        this.$nextTick(()=>{
            this.op = getOp()
        })
    },
}

</script>
<style lang='less'>
.contact_with_us{
    .bord{
        width: 70px;
        position: absolute;
        left: -120px;
        top:24px;
        border: 1px solid #fff;
    }
    .colorbox{
        // background: #f97f54;
        background-image: linear-gradient(30deg, #f98054  0%, #ef4072 100%);
    }
}
</style>