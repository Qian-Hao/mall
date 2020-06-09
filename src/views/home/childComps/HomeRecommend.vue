<template>
    <div class="recommend">
        <div v-for="item in recommends" class="recommend-item">
            <a :href="item.link">
                <img :src="item.image" alt="">
                <div>{{item.title}}</div>
            </a>
        </div>
    </div>
</template>

<script>
    export default {
        name: "HomeRecommend",
        props: {
            recommends: {
                type: Array,
            }
        }
    }
</script>

<style scoped>
    a {
        text-decoration: none;
        color: gray;
    }

    .recommend {
        display: flex;
        text-align: center;
        font-size: 12px;
        padding: 15px 0 30px;
        color: black;
    }

    .recommend-item {
        flex: 1;
    }

    .recommend-item img {
        width: 65px;
        height: 65px;
    }
</style>