<template>
    <div class="width_100 head_com display_flex position_absolute" :class="{height_250px: show_option}" style="z-index: 1000">
        <div class="display_flex media_flex_row_800 flex_jusify_space flex_align_center width_80 margin_auto">
            <!-- 左面的logo -->
            <img
                v-if="$store.state.scroll_top > 10"
                src="../../static/img/loog2.png"
                style="width:200px;"
                alt
            />
            <img v-else src="../../static/img/loog1.png" style="width:200px;" alt />
            <!-- 右面的 -->
            <div :class="{'width_100': !$store.state.is_pc}">
              <img src="../../static/img/xm.png" @click="show_option=!show_option" class="phone_show" style="width:30px;" alt="">
              <div
                  class="display_flex transition_1-2s right_text"
                  :class="{'scale_y': !show_option, 'margin_top_10': !$store.state.is_pc }"
              >
                  <div class="t1 margin_left_14 font_size_20" v-for="(item,index) in arr" :class="{'selectedOption': selectedOption==index}" @click="clickHead(item,index)" :key="item">{{item}}</div>
              </div>
            </div>
        </div>
    </div>
</template>

<script>
import videoButton from "../button";
import getCountry from "../../util/get_country";
import bus from "../../util/bus";
import unlogin from "../../util/unlogin";
import getOp from "../../util/get_country";

export default {
  methods:{
    clickHead(v, i){
      this.$emit("clickHead", v)
      this.selectedOption = i
    },
  },
  data (){
    return {
      arr: ["Home", "About", "Contact Us"],
      show_option: true,
      selectedOption: -1,
    }
  },
};
</script>

<style lang='less'>


.head_com {
    top: 0;
    height: 100px;
    background: transparent;

    &.top_50px {
        box-shadow: 2px 2px 2px rgba(200, 200, 200, 0.5);
        background: #fff;
        top: 0px !important;
        transition-duration: 1.4s;
        .right_text{
          color: #000;
        }
    }
    &.notop {
        background: #fff !important;
    }
    .right_text {
        color: #fff;
        .t1 {
            font-weight: 400;
        }
    }
}

@media screen and (max-width: 800px){
    .scale_y{
      // height: 0;
      transform: scaleY(0);
    }
    .head_com{
      &.height_250px{
        height: 250px;
      }
      display: block;
      .right_text{
        div{
          padding: 10px;
          color: #fff;
          &.selectedOption {
            color: #000;
          }
        }
        transform-origin: 0 0;
        overflow: hidden;
        display: block;
        text-align: center;
        background: #262626;
        width: 100%;
      }
    }

}

</style>
