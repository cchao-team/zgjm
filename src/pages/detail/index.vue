<template>
  <div class="detailwrap">
    <div class="header">
      <img src="/static/images/logo.png" alt="logo">
    </div>
   <div class="main">
        <div class="item">
          <p class="item_tit">{{title}}</p>
          <p class="item_con">{{context}}</p>
        </div>
         <div class="list" v-for="(item, index) in contentList" :key="index">
           <div class="list_item">
              <div class="item-top">
                <em>梦</em>
                <span>{{item.list_tit}}</span>
              </div>
              <div class="item-center">
                <p>{{item.list_con}}</p>
              </div>
           </div>
      </div>
    </div> 
  </div>
</template>

<script>
export default {
  data () {
    return {
      query: '',
      title: '梦见双胞胎',
      context: '可以象征鑫哥哥的相互对立同时又相互统一的两个方面，同时也反映做梦人相互对立的个性。',
      contentList: [
        {
          list_tit: '自己怀了双胞胎',
          list_con: '可以象征鑫哥哥的相互对立同时又相互统一的两个方面，同时也反映做梦人相互对立的个性。'
        },
        {
          list_tit: '自己怀了双胞胎',
          list_con: '可以象征鑫哥哥的相互对立同时又相互统一的两个方面，同时也反映做梦人相互对立的个性。'
        },
        {
          list_tit: '自己怀了双胞胎',
          list_con: '可以象征鑫哥哥的相互对立同时又相互统一的两个方面，同时也反映做梦人相互对立的个性。'
        }
      ]
    }
  },
  mounted () {
    console.log(this.$route)
  }
}
</script>
<style lang="scss" scoped>
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
.detailwrap{
  .header{
    width: 750rpx;
    height: 150rpx;
    @extend .center;
    img {
        width: 246rpx;
	      height: 70rpx;
      }
  }
  .main{
    .item{
      padding: 48rpx 52rpx 45rpx 40rpx;
	    border-bottom:1px solid #c1c8d0;
      .item_tit{
        width: 100%;
        text-align: center;
        font-family: PingFangSC-Semibold;
        font-size: 38rpx;
        font-weight: normal;
        font-stretch: normal;
        line-height: 32rpx;
        letter-spacing: 0rpx;
        color: #068bc9;
        margin-bottom: 43rpx;
      }
      .item_con{
        font-family: PingFangSC-Regular;
        font-size: 32rpx;
        font-weight: normal;
        font-stretch: normal;
        line-height: 54rpx;
        letter-spacing: 0rpx;
        color: #4c4f51;
        text-indent: 64rpx;
      }
    }
    .list{
      padding-left:40rpx;
      .list_item{
         padding: 48rpx 52rpx 45rpx 0;
         border-bottom:1px solid #c1c8d0;
        .item-top{
        width: 100%;
        text-align: left;
        margin-bottom: 43rpx;
        em,span{
          display: inline-block;
          vertical-align: middle;
        }
        em{
          width: 40rpx;
          height: 40rpx;
          border-radius: 50%;
          background-color: #068bc9;
          font-family: TpldKhangXiDictDemo;
          font-size: 24rpx;
          font-weight: normal;
          font-stretch: normal;
          line-height: 40rpx;
          letter-spacing: 0rpx;
          color: #ffffff;
          text-align: center;
          margin-right: 20rpx;
        }
        span{
          font-family: PingFangSC-Medium;
          font-size: 34rpx;
          font-weight: normal;
          font-stretch: normal;
          line-height: 32rpx;
          letter-spacing: 0rpx;
          color: #068bc9;
        }
      }
      .item-center{
        font-family: PingFangSC-Regular;
        font-size: 32rpx;
        font-weight: normal;
        font-stretch: normal;
        line-height: 54rpx;
        letter-spacing: 0rpx;
        color: #4c4f51;
        text-indent: 64rpx;
      }
      }
      &:last-child{
        border-bottom: 0;
      }
    }
  }
}
 
</style>
