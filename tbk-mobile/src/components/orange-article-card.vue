<template>

    <!--文章卡片-->

    <div style="background-color: #fff" @click="open(to)">

        <van-row type="flex" justify="center" style="padding-top: 10px;padding-bottom: 5px">
            <van-col span="22">
                <img :src="image" height="150px" width="100%" />
            </van-col>
        </van-row>

        <van-row type="flex" justify="center" style="padding-top: 10px;padding-bottom: 5px">
            <van-col span="22">
                <span>{{ title }}</span>
            </van-col>
        </van-row>

        <van-row type="flex" justify="center">
            <van-col span="22"><hr></van-col>
        </van-row>

        <van-row type="flex" justify="center" style="padding-bottom: 10px">
            <van-col span="22">

                <van-row type="flex" justify="center">
                    <van-col span="12">
                        <span style="color: darkgray;font-size: 13px">{{ author }}</span>
                    </van-col>
                    <van-col span="12" style="display: flex;flex-direction: row;justify-content:flex-end;">
                        <div>
                            <van-icon style="color: darkgray;font-size: 13px" name="underway-o" />
                            <span style="color: darkgray;font-size: 13px;margin-left: 3px">{{ date }}</span>
                        </div>
                        <div v-if="visit != null" style="margin-left: 10px">
                            <van-icon style="color: darkgray;font-size: 13px" name="eye-o" />
                            <span style="color: darkgray;font-size: 13px;margin-left: 3px">{{ visit }}</span>
                        </div>
                    </van-col>
                </van-row>

            </van-col>
        </van-row>

    </div>

</template>

<script>
    export default {
        name: "orange-article-card",
        props:["title","image","author","date","visit","to"],
        methods: {
            open(to) {
                this.$router.push({ path: to });
            },
        },
    }
</script>

<style scoped>
    hr {
        background-color:#E4E7ED;height:1px;border:none;
    }
</style>
