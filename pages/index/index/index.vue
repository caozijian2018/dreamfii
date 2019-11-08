<template>
    <div class="home_page height_100 overflow_scroll" @scroll="scroll">
        <div>
            <!-- :class="{'top_50px': $store.state.scroll_top > 50 && $store.state.scroll_top < 150, 'notop':$store.state.scroll_top > 10}" -->
            <!-- :class="{'top-100': $store.state.scroll_top > 100}" -->
            <!-- {{$store.state.scroll_top}} -->
            <video-head
                @clickHead="clickHead"
                :class="{'top_50px': $store.state.scroll_top > 100}"
                :style="{'top': '-'+$store.state.scroll_top+'px'}"
            ></video-head>
            <video-banner></video-banner>
            <!--  -->
            <h1 class="third_div_title font_size_21 text_center margin_top_4 margin_bottom_3">
                What We Do
            </h1>
            <div class="third_div margin_bottom_3 margin_top_3 padding_bottom_30">
                <div class="width_80_pc margin_auto media_flex_row_800 intro_parent display_flex flex_jusify_space">
                    <div
                        v-for="(item,index) in list1"
                        :key="item.title"
                        @click="selectedIndex=index"
                        :class="{selected_what_we_do_option_index: selectedIndex==index}"
                        class="intro  display_flex flex_column flex_center flex_align_center"
                    >
                        <img :src="item.img" alt />
                        <div class="font_size_15">{{item.title}}</div>
                    </div>
                </div>
                <div class="display_flex what_wedo_info_box width_80_pc margin_top_4 margin_auto flex_jusify_space">
                    <div class="width_45">
                        <h1 class="margin_bottom_3 font_size_30">{{list1[selectedIndex].title}}</h1>
                        <div class="line_height_35px font_size_20 gray" style="line-height: 35px;">
                            {{list1[selectedIndex].txt}}
                        </div>
                    </div>
                    <img class="width_45 phone_width_100" :src="list1[selectedIndex].bigimg" alt />
                    <!-- <h2 class="flex_1">
                        xx
                    </h2> -->
                </div>
            </div>
            <h1 class="font_size_21 text_center margin_top_4 margin_bottom_3">
                Our Partners
            </h1>
             <partener></partener>
             <h1 class="font_size_21 text_center margin_top_4 margin_bottom_3">
                Our Services
            </h1>
            <!-- <video-banner></video-banner> -->
            <div class="width_80_pc margin_auto display_flex flex_jusify_space margin_bottom_4">
               

                <!-- <div class="width_30 text_center" v-for="item in list4" :key="item.title">
                    <img :src="item.img" class="width" alt="">
                </div> -->
                
                <!-- {{list4Result.length}}
                <el-carousel height="100px" :interval="5000" arrow="always">
                    <el-carousel-item v-for="item in list3" :key="item.title" class="display_flex flex_jusify_space">
                        asdasd
                        <img v-for="img_obj in item" :key="img_obj.title" :src="img_obj.img" alt="" class="width_100">
                    </el-carousel-item>
                </el-carousel> -->
            </div>
            <div class="width_80_pc margin_auto display_flex phone_block flex_jusify_space margin_bottom_4">
                <div class="width_30 phone_width_100 text_center phone_margin_bottom_20" v-for="item in list2" :key="item.title">
                    <img :src="item.bigimg" class="width_100 phone_width_90" alt="">
                    <div class="margin_bottom_2 margin_top_10 font_size_15 gray phone_margin_auto phone_width_90">
                        {{item.txt}}
                    </div>
                </div>
            </div>
            <div class="text_center">
                <h1>
                    Contact Us
                </h1>
            </div>
            <!-- 邮箱 -->
            <div class="map_">
                <div class="width_80_pc margin_auto display_flex flex_jusify_space phone_block phone_width_90">
                    <div class="width_45 phone_width_90 phone_margin_auto">
                        <h1 class="margin_bottom_3">
                            Contact Info
                        </h1>
                        <div class="display_flex margin_bottom_3 flex_align_center" v-for="item in list3" :key="item.title">
                            <div class="display_flex icon_ flex_center flex_align_center">
                                <img :src="item.img" style="width:50px;" class="vertical_middle" alt="">
                            </div>
                            <div class="margin_left_14 flex_1">
                                <h1 class="margin_bottom_15">
                                   {{item.title}}
                                </h1>
                                <div class="font_size_15">
                                    {{item.txt}}
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="width_45 phone_width_90 phone_margin_auto">
                        <h1 class="margin_bottom_3">
                            Contact Form
                        </h1>
                        <input type="text" v-model="name" placeholder="Full name" class="margin_bottom_3 display_block dreamfiiinput">
                        <input type="text" v-model="email" placeholder="Email" class="margin_bottom_3 display_block dreamfiiinput">
                        <textarea name="" v-model="message" id="" cols="30" placeholder="Message" class="textarea dreamfiiinput display_block" rows="3"></textarea>
                        <button class="submit margin_top_4" @click="submit">SUBMIT</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import bus from "../../../util/bus";
import videoBanner from "../../../components/banner";
import partener from "../../../components/partener";
import videoHead from "../../../components/videoHead";

export default {
    components: {
        videoBanner,
        videoHead,
        partener
    },
    mounted() {
        this.whatchScroll();
        console.log(8888);
        console.log(this.list4Result);
    },
    computed:{
        list4Result(){
            var result = [];
            var data = this.list4;
            for(var i=0;i<data.length;i+=3){
                result.push(data.slice(i,i+3));
            }
            return result
        }
    },
    data() {
        return {
            name:"",
            email:"",
            message:"",
            selectedIndex: 0,
            list1: [
                {
                    img: require("../../../static/img/l1.png"),
                    bigimg: require("../../../static/img/w1.jpg"),
                    title: "CONTENT PROVIDER",
                    txt: "Dreamfii is a digital content provider aiming at providing premium services to global mobile users. With our services, users can enjoy a wide range of game, music and video content on their phones. Our model lets users subscribe for unlimited entertainment resources without adds. "
                },
                {
                    img: require("../../../static/img/l2.png"),
                    bigimg: require("../../../static/img/w2.jpg"),
                    title: "ADVERTISING SOLUTIONS",
                    txt: "Based on user analysis and market investigation, Dreamfii provides advertising solutions for companies that want to promote products in global market. With experienced media buying team, professional affiliate network and publisher team, we offer advertising services to more than 1000 companies word wide. "
                }
            ],
            list2: [
                {
                    bigimg: require("../../../static/img/service1.png"),
                    title: "Charm Garden",
                    txt: "Charm Garden is a premium subscription service dedicated to attractive mobile charming videos, such as bikini, long legs, beautiful tits, cute and big ass, hot, pretty and sexy blonde, etc. "
                },
                {
                    bigimg: require("../../../static/img/service2.png"),
                    title: "Game Park",
                    txt: "Game Park is a premium subscription service portal focused on high-quality mobile games. The types of games include strategy, shooting, action, sports, role-playing, adventure, racing, fighting, etc."
                },
                {
                    bigimg: require("../../../static/img/service3.png"),
                    title: "Humor Boom",
                    txt: "Humor Boom is a premium subscription service dedicated to hilarious mobile videos. Subscribers can enjoy the videos whenever they feel bored and want some fun. "
                }
            ],
//             Address: ROOM 3 27/F HO KING COMMERCIAL CENTRE NO 2-16 FA YUEN STREET MONGKOK KL
// E-Mail: Customer@dreamfii.com
            list3: [{
                img: require("../../../static/img/addr.png"),
                title: "Address",
                txt: "ROOM 3 27/F HO KING COMMERCIAL CENTRE NO 2-16 FA YUEN STREET MONGKOK KL",

            },
            {
                img: require("../../../static/img/email.png"),
                title: "Email",
                txt: "Customer@dreamfii.com"
                }
            ],
            
            list4: [{
                img: require("../../../static/img/fb.png"),
                title: "Facebook",
            },
            {
                img: require("../../../static/img/google.png"),
                title: "Google",
                },
            
            {
                img: require("../../../static/img/truemove.jpg"),
                title: "Truemove",
            },
            {
                img: require("../../../static/img/digi.png"),
                title: "Digi",
            },
            {
                img: require("../../../static/img/dtac.jpg"),
                title: "Dtac",
            },
            {
                img: require("../../../static/img/celcom.jpg"),
                title: "Celcom",
            },
            {
                img: require("../../../static/img/vodafone.png"),
                title: "Vodafone",
            },
            {
                img: require("../../../static/img/orange.jpg"),
                title: "Orange",
            },
            {
                img: require("../../../static/img/O2.png"),
                title: "O2",
            }
            ]
        };
    },
    methods: {
        clickHead(v){
            switch (v){
                case "Home":(()=>{
                    this.$jquery('.home_page').animate({scrollTop: 0},1000);
                })();break;
                case "Contact Us":(()=>{
                    this.$jquery('.home_page').animate({scrollTop: 10000},1000);
                })();break;
                case "About":(()=>{
                    this.$jquery('.home_page').animate({scrollTop: document.querySelector(".third_div_title").offsetTop},1500);
                })();break;
            }
            
        },
        scroll(v) {
            var scrollTop = v.target.scrollTop;
            bus.$emit("windowScroll", scrollTop);
        },
        submit(){
            setTimeout(()=>{
                this.name = ""
                this.email = ""
                this.message = ""
                this.$msg("Send Success")
            },1000)
        },
        whatchScroll() {
            bus.$on("windowScroll", v => {
                this.$store.state.scroll_top = v;
            });
        }
    }
};
</script>
<style lang='less'>
.home_page {
    .third_div {
        .intro {
            &.selected_what_we_do_option_index{
                background: skyblue;
                color: #fff;
            }
            height: 200px;
            width: 20%;
            border-radius: 5px;
            background: #f4f4f4;
            color: #222222;
            display: flex;
            img{
                width: 100px;
                height: 100px;
                border-radius: 50%;
            }
        }
    }
    .map_{
        background-image: url("../../../static/img/world-map.png");
        background-size: 100%;
        padding-bottom: 70px;
        .submit{
            box-shadow: 4px 4px 4px #ddd;
            box-sizing: border-box;
            color: #fff;
            font-size: 16px;
            height: 40px;
            border-radius: 20px;
            background: skyblue;
            text-align: center;
            padding: 0px 20px;
        }
        .icon_{
            width: 70px;
            height: 70px;
            text-align: center;
            border: 1px solid #ddd;
            border-radius: 50%;
        }
        .dreamfiiinput{
            height: 60px;
            box-sizing: border-box;
            border-radius: 30px;
            background: #fff;
            border: 1px solid #ddd;
            width: 100%;
            font-size: 25px;
            padding-left: 20px;
            box-shadow: 5px 5px 5px #ddd;
            &.textarea{
                height:auto;
                padding-left: 20px;
            }
        }
        
    }
}

@media screen and (max-width: 800px){
.home_page {
    .third_div {
        .what_wedo_info_box{
            display: block;
            &>div{
                width: 90%;
                margin:auto
            }
        }
        .intro {
            height: 200px;
            width: 100%;
            border-radius: 5px;
            background: #f4f4f4;
            color: #222222;
            display: flex;
        }
    }

}
}
</style>