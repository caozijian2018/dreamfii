<template>
    <div class="height_100 overflow_scroll scroll_box_div" @scroll="scroll">
        <!-- <div class="position_fixed width_100 headerrr">
            <img src="../../../static/img/logo2.png" style="width: 100px" class="padding_left_20" alt="">
        </div>-->
        <div class="position_fixed width_100 head_div vertical_middle" style="z-index:1000000">
            <img
                :src="scroll_top < 700 ? logowhite : logored"
                class="head_img vertical_middle padding_left_30"
                alt
            />
        </div>
        <div class="hoverdiv" style="background: #ef4072;z-index:10004" v-if="show_loading">
            <img
                src="../../../static/img/loading.gif"
                class="loading_img width_70 phone_width_100 pcs"
                alt
            />
        </div>
        <!-- banner -->
        <banner
            @tobottom="jump()"
            :class="{
        transition_back: most_scroll_y + $store.state.innerHeight > show_arr[0]
      }"
        ></banner>
        <about
            :class="{
        transition_back: most_scroll_y + $store.state.innerHeight > show_arr[1]
      }"
            ref="about"
            class="margin_top_70px phone_margin_top_160px"
        ></about>
        <contentProvider
            :img1="imgcontent1"
            :img2="imgcontent2"
            :text1="c1text1"
            :text2="c1text2"
            :text3="c1text3"
            class="margin_top_70px"
            :top-down-distance="show_arr[2] - scroll_top"
            :class="{
        transition_back:
          most_scroll_y + $store.state.innerHeight / 1.5 > show_arr[2]
      }"
            ref="content_provider"
        ></contentProvider>
        <contentProvider2
            :img1="imgcontent2_1"
            :img2="imgcontent2_2"
            :text1="c2text1"
            :text2="c2text2"
            :text3="c2text3"
            :top-or-down="scroll_top > show_arr[3]"
            class="margin_top_70px"
            :top-down-distance="show_arr[3] - scroll_top"
            :class="{
                transition_back:
                most_scroll_y + $store.state.innerHeight / 1.5 > show_arr[3]
            }"
            ref="content_provider_2"
        ></contentProvider2>
        <work-with-us 
            :class="{
                transition_back: most_scroll_y + $store.state.innerHeight/1.5 > show_arr[4]
            }" 
            ref="work_with_us" 
            class="margin_top_70px">
        </work-with-us>
        <contentProvider
            :img1="imgcontent3_1"
            :img2="imgcontent3_2"
            :text1="c1text3_1"
            class="margin_top_70px"
            :text2="c1text3_2"
            :text3="c1text3_3"
            :top-down-distance="show_arr[5] - scroll_top"
            :class="{
        transition_back:
          most_scroll_y + $store.state.innerHeight / 1.5 > show_arr[5]
      }"
            ref="content_provider_3"
        ></contentProvider>
        <contentProvider2
            :img1="imgcontent4_1"
            :img2="imgcontent4_2"
            :text1="c2text5"
            :text2="c2text6"
            :text3="c2text7"
            :top-down-distance="show_arr[6] - scroll_top"
            :class="{
        transition_back:
          most_scroll_y + $store.state.innerHeight / 1.5 > show_arr[6]
      }"
            ref="content_provider_4"
        ></contentProvider2>
        <contact-us ref="contact_us" class="margin_top_70px"
            :class="{
                transition_back: most_scroll_y + $store.state.innerHeight > show_arr[7]
            }" 
        >
        </contact-us>
        <app-footer class="margin_top_70px"></app-footer>
        <!-- <img src="../../../static/img/back/office.gif" class="width_100" alt=""> -->
        <!-- <contentProvidert class="margin_top_70px" :top-or-down="scroll_top > show_arr[4]" :class="{'transition_back': most_scroll_y + $store.state.innerHeight > show_arr[4]}" ref="content_provider_3"></contentProvidert>
        <contentProviderw class="margin_top_70px" :top-or-down="scroll_top > show_arr[5]" :class="{'transition_back': most_scroll_y + $store.state.innerHeight > show_arr[5]}" ref="content_provider_4"></contentProviderw>-->
    </div>
</template>

<script>
import pcOrPhone from "../../../util/get_pc_or_phone";
import banner from "../../../components/banner";
import about from "../../../components/about";
import contentProvider from "../../../components/content_provider";
import contentProvider2 from "../../../components/content_provider_";
import workWithUs from "../../../components/work_with_us";
import contactUs from "../../../components/contact_us";
import appFooter from "../../../components/footer";

export default {
    components: {
        banner,
        about,
        contentProvider,
        contentProvider2,
        workWithUs,
        contactUs,
        appFooter
    },
    mounted() {
        this.init();
        this.sortOffsetY();
    },
    data() {
        return {
            show_loading: true,
            logowhite: require("../../../static/img/logo2.png"),
            logored: require("../../../static/img/logo.png"),

            scroll_top: 0,
            most_scroll_y: 0,
            show_arr: [],
            imgcontent1: require("../../../static/img/back/1.jpg"),
            imgcontent2: require("../../../static/img/back/1-2.gif"),
            c1text1: "CONTENT PROVIDER",
            c1text2:
                "Dreamfii is a digital content provider aiming at providing premium services to global mobile users. ",
            c1text3:
                "With our services, users can enjoy a wide range of game, music and video content on their phones. Our model lets users subscribe for unlimited entertainment resources without adds. ",

            imgcontent2_1: require("../../../static/img/back/2.jpg"),
            imgcontent2_2: require("../../../static/img/back/2iphone_.png"),
            c2text1: "VIDEO PORTAL",
            c2text2: "Taichi-lifestyle Video Portal",
            c2text3:
                "Taichi-lifestyle is a premium subscription service portal focused on high-quality Taichi and Kungfu videos. Users can browse the videos online after they subscribe successfully. The content is divided into the following categories: common Taichi video, relaxing video, men’s video, women's video, outdoor video, powerful video, other martial arts and video of people with weapons. It’s widely enjoyed by overseas users. ",
            imgcontent3_1: require("../../../static/img/back/3.jpg"),
            imgcontent3_2: require("../../../static/img/back/3-2.gif"),
            c1text3_1: "ADVERTISING SOLUTIONS",
            c1text3_2: "Get overseas users from now!",
            c1text3_3:
                "Based on user analysis and market investigation, Dreamfii provides advertising solutions for companies that want to promote products in global market. ",
            imgcontent4_1: require("../../../static/img/back/4.jpg"),
            imgcontent4_2: require("../../../static/img/back/4-2.gif"),
            c2text5: "PROFESSIONAL TEAM",
            c2text6: "Let us help promote your products!",
            c2text7:
                "With experienced media buying team, we offer advertising services to more than 1000 companies word wide, including some Internet giants at home and abroad. We provide media marketing solutions and global traffic integration solutions to enterprises and help them display the brand value in the world."
        };
    },
    methods: {
        jump() {
            this.$jquery(".scroll_box_div").animate({ scrollTop: 8000 }, 2000);
        },
        sortOffsetY() {
            this.$nextTick(() => {
                this.show_arr = [
                    0,
                    this.$refs.about.$el.offsetTop,
                    this.$refs.content_provider.$el.offsetTop,
                    this.$refs.content_provider_2.$el.offsetTop,
                    this.$refs.work_with_us.$el.offsetTop,
                    this.$refs.content_provider_3.$el.offsetTop,
                    this.$refs.content_provider_4.$el.offsetTop,
                    this.$refs.contact_us.$el.offsetTop
                ];
            });
        },
        scroll(v) {
            var scroll_top = v.target.scrollTop;
            this.scroll_top = scroll_top;
            if (scroll_top > this.most_scroll_y) {
                this.most_scroll_y = scroll_top;
            }
        },
        init() {
            this.setHeightAndPhoneOrPc();
            this.watchOnresize();
            setTimeout(() => {
                this.show_loading = false;
            }, 3000);
        },
        watchOnresize() {
            window.onresize = this.setHeightAndPhoneOrPc;
        },
        setHeightAndPhoneOrPc() {
            this.$store.state.innerHeight = innerHeight;
            this.$store.state.innerWidth = innerWidth;
            this.$store.state.is_pc = pcOrPhone();
        }
    }
};
</script>
<style lang="less">
.head_div {
    height: 100px;
    line-height: 100px;
    .head_img {
        height: 23px;
    }
}
.loading_img {
    // width: 200px;
}
</style>
