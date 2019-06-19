<template>
  <div class="detailwrap">
    <div class="header">
      <img src="/static/images/logo.png" alt="logo">
    </div>
    <div class="main">
        <div class="item">
          <p>{{title}}</p>
          <p>{{content}}</p>
        </div>
        <div class="list-item" v-for="(item, index) in contentList" :key="index">
          <div class="item-top">
            <img src="/static/images/icon.png" alt="icon">
            <span>{{item.list_title}}</span>
          </div>
          <div class="item-center">
            <p>{{items.content}}</p>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title:'梦见双胞胎',
      content:'可以象征鑫哥哥的相互对立同时又相互统一的两个方面，同时也反映做梦人相互对立的个性。',
      contentList:[
        {
          list_title:'自己怀了双胞胎',
          list_content:'可以象征鑫哥哥的相互对立同时又相互统一的两个方面，同时也反映做梦人相互对立的个性。'
        },
        {
          list_title:'认识梦里的双胞胎',
          list_content:'可以象征鑫哥哥的相互对立同时又相互统一的两个方面，同时也反映做梦人相互对立的个性。'
        }
      ]
    }
  },
  mounted () {
    console.log(123)
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

  }
}
</style>
