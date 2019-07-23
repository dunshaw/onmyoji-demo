<template>
    <div class="homepage">
        <swiper indicator-dots autoplay="true" interval="4000" circular="true" indicator-color="rgba(255, 255, 255, .3)" indicator-active-color="rgba(255, 255, 255, .8)">
            <swiper-item v-for="item in swipers" :key="item.id">
                <img :src="item" alt="" >
            </swiper-item>
        </swiper>
        <div>
            <Lists />
        </div>    
    </div>
</template>
<script>
import Lists from '@/components/Homes/lists'

export default {
    data(){
        return {
            swipers:[
                '/static/images/home-swiper/1.jpg',
                '/static/images/home-swiper/4.jpg',
                '/static/images/home-swiper/2.jpg',
                '/static/images/home-swiper/3.jpg',
                '/static/images/home-swiper/5.jpg',
            ]
        }
    },
    components: {
        Lists,
    },
}
</script>
<style scoped>
    .homepage swiper{
        width: 100%;
        height: 400rpx;
    }
    .homepage swiper img{
        width: 100%;
        height: 100%;
    }
</style>