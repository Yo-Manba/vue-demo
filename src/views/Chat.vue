<template>
    <div>
        <Header :hasBack="false" :title="'首页'" />
        <HomePage ref="homePage">
            <div>
                <van-button type="default" @click="clickHandler"
                    >默认按钮</van-button
                >
                <van-button type="primary">主要按钮</van-button>
                <van-button type="info">信息按钮</van-button>
                <van-button type="warning">警告按钮</van-button>
                <van-button type="danger">危险按钮</van-button>
            </div>

            <van-image
                width="100"
                height="100"
                fit="cover"
                src="https://img.yzcdn.cn/vant/cat.jpeg"
            />

            <div>Lambert修改了代码</div>
            <div>Lambert增加了新代码</div>
            <div>YY修改了代码</div>
            <div>这是dev分支的修改</div>
            <div>这是slide分支的修改</div>

            <van-cell is-link @click="showPopup">展示弹出层</van-cell>

        </HomePage>

        <van-popup v-model="show" position="bottom">
            <div v-for="(item, index) of 100" :key="index">啥客户</div>
        </van-popup>
    
    </div>
</template>

<script>
import Header from "../components/Header";
import HomePage from "../components/HomePage";

export default {
    name: "Chat",
    data() {
        return {
            show: false
        };
    },
    components: {
        Header,
        HomePage
    },

    methods: {
        clickHandler(item) {
            this.$router.push({ name: "towPage", params: { info: item } });
        },

        showPopup() {
            this.show = true;
        }
    },

    beforeCreate() {
        console.log("chat beforeCreate");
    },

    created() {
        console.log("chat created");
    },

    beforeMount() {
        console.log("chat beforeMount");
    },

    mounted() {
        console.log("chat mounted");
        this.$refs.homePage.init();
    },
    
    beforeUpdate() {
        console.log("chat beforeUpdate");
    },

    updated() {
        console.log("chat updated");
    },

    beforeDestroy() {
        console.log("chat beforeDestroy")
    },

    destroyed() {
        console.log("chat destroyed")
    },

    activated() {
        console.log("chat activated");
    },
};
</script>

<style lang="stylus" scoped>
// 按钮
.van-button--normal {
    padding: 0 0.3rem;
    font-size: 0.28rem;
}

// 弹出层
.van-popup--bottom {
    height: 8rem;
    border-top-left-radius: 0.2rem;
    border-top-right-radius: 0.2rem;
    padding: 0.2rem;
    box-sizing: border-box;
}
</style>
