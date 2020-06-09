<template>
    <div id="home">
        <nav-bar class="nav-bar"><div slot="center">购物街</div></nav-bar>
        <home-swiper :banners="banners"></home-swiper>
        <home-recommend :recommends="recommends"></home-recommend>
    </div>
</template>

<script>
    import NavBar from "components/common/navbar/NavBar";
    import {getHomeMultidata} from "../../network/home";
    import HomeSwiper from "./childComps/HomeSwiper";
    import HomeRecommend from "./childComps/HomeRecommend";

    export default {
        name: "Home",
        components: {
            NavBar,
            HomeSwiper,
            HomeRecommend
        },
        data() {
            return {
                banners: [],
                recommends: []
            }
        },
        created() {
            getHomeMultidata().then(res => {
                console.log(res);
                this.banners = res.data.banner.list;
                this.recommends = res.data.recommend.list;
            })
        }
    }
</script>

<style scoped>
    .nav-bar {
        background-color: hotpink;
        font-weight: 700;
        color: #fff;
    }

</style>