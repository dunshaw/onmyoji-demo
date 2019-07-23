<template>
    <div class="indexContainer">
        <img class="index_img" src="/static/images/test1.jpeg" alt="" v-if="showflag">
        <button class="mbtn" open-type="getUserInfo" @getuserinfo="getuserInfo" v-else="showflag">获取用户信息</button>
        <p class="index_welcome">welcome</p>
        <p class="userName">{{userInfo.nickName}}</p>
        <div @tap='goToDetail'>
            <p class="startBtn">开启小程序之旅</p>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            userInfo:{},
            showflag:false,
        }
    },
    beforeMount() {
        this.handleUserinfo()
    },
    methods: {
        // 获取用户信息
        handleUserinfo(){
            wx.getUserInfo({
                success:data=>{
                    console.log(data)
                    this.userInfo = data.userInfo
                    this.showflag = true;
                },
                fail:()=>{
                    this.showflag = false;
                    console.log('failed!')
                }
            })
        },
        getuserInfo(data){
            // 判断用户是否授权
            if(data.mp.detail.rawData){
                this.handleUserinfo()
            }
            console.log(data)
        },
        // 跳转页面
        goToDetail(){
            console.log('gogogogtototo')
            wx.navigateTo({
                url:'/pages/home/main'
            })
        },
    },
}
</script>
<style scoped>
    page{
        background: #8ed145;
    }
    .indexContainer{
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .index_img{
        width:200rpx;
        height: 200rpx;
        border-radius: 100rpx;
        margin: 100rpx 0;
    }
    .index_welcome{
        font-size: 60rpx;
        font-weight:bold;
        letter-spacing: 5rpx;
        color:antiquewhite;
    }
    .userName{
        font-size: 40rpx;
        font-weight: bold;
        margin: 100rpx 0;
    }
    .startBtn{
        width: 220rpx;
        height: 80rpx;
        border: 1px solid #eee;
        font-size: 24rpx;
        line-height: 80rpx;
        text-align: center;
        border-radius: 10rpx;
    }
    .mbtn {
        width: 300rpx;
        height: 300rpx;
        border-radius: 150rpx;
        margin:100rpx 0;
        font-size: 26rpx;
        line-height: 300rpx;
        text-align: center;
    }
</style>