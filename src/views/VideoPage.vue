
<template>
    <div>
        <Header :hasBack="true" :title="'VideoPage'" />
        <InnerPage
            ref="innerPage"
            :pulldown="false"
            :pullup="false"
            :pullupTxt="false"
        >
            <Video :videoIndex='0' />
            <Video :videoIndex='1' />
        </InnerPage>
    </div>
</template>

<script>
import Header from "../components/Header";
import InnerPage from "../components/InnerPage";
import Video from "../components/Video";

export default {
    name: "VideoPage",
    data() {
        return {
            showPlay: true,
            showPause: false
        };
    },

    components: {
        Header,
        InnerPage,
        Video
    },

    computed: {},

    methods: {
        


        /**
         * 页面相关事件处理函数--监听用户下拉动作
         */
        async onPullDownRefresh() {
            return new Promise(resolve => {
                // 数据请求完成后执行resolve(), 程序才会继续进行
                resolve();
            });
        },

        /**
         * 页面上拉触底事件的处理函数
         */
        async onReachBottom() {
            return new Promise(resolve => {
                // 数据请求完成后执行resolve(), 程序才会继续进行。可在resolve方法中传入false参数，在没有更多可加载数据时使用
                resolve(false);
            });
        }
    },

    mounted() {
        this.$refs.innerPage.init();
    },

    activated() {}
};
</script>

<style lang='less' scoped>

</style>