<template>
  <div>
    <header>
        <img src="/static/images/title_1.png" alt="" class="title">
    </header>
    <section>
        <div class="box" v-for="item in news" :key="item.id">
            <div class="leftitem">
                <h2>{{ item.h2 }}</h2>
                <p>{{ item.p }}</p>
                <span>{{ item.span }}</span>
            </div>
            <div class="rightitem"><img :src="item.img" alt=""></div>
        </div>
    </section>
  </div>
</template>

<script>

  export default {
    name:'',
    props:[''],
    data () {
      return {
          news:[
              {'img':'/static/images/home-news/list1.png','h2':'新弑神降临','p':'hahaha','span':'2019-5-2'},
              {'img':'/static/images/home-news/list2.jpeg','h2':'新弑神降临','p':'hahaha','span':'2019-5-1'},
              {'img':'/static/images/home-news/list3.jpeg','h2':'新弑神降临','p':'hahaha','span':'2019-5-1'},
              {'img':'/static/images/home-news/list4.jpeg','h2':'新弑神降临','p':'hahaha','span':'2019-4-30'},
          ],
      };
    },

    components: {},

    computed: {},

    beforeMount() {},

    mounted() {},

    methods: {
        
    },

    watch: {}

  }

</script>
<style lang='' scoped>
    .title{
        height: 45rpx;
        width: 100%;
        margin: 20rpx 0;
        margin-bottom: 10rpx;
    }
    .box{
        width: 96%;
        margin:10rpx auto;
        padding: 10rpx;
        /* border: 1px solid #eee; */
        border-radius: 10rpx;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: center;
        background: #eee;
    }
    .leftitem{
        width: 400rpx;
        word-wrap: break-word;
        text-overflow:ellipsis;
        overflow: hidden; 
        align-self: space-between;
    }
    span{
        font-size: 20rpx;
    }
    .rightitem{
        width: 200rpx;
        height: 200rpx;
    }
    .rightitem img{
        width: 200rpx;
        height: 200rpx;
        border-radius: 5rpx;
    }
</style>