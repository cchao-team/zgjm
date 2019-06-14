<template>
  <div class="wrapper">
    <div class="header">
      <div class="logo">
        <img src="/static/images/logo.png" alt="logo">
      </div>
      <div class="search-input">
        <span>梦见：</span><input type="text" v-model="query" placeholder="蛇、打雷">
      </div>
      <div class="search-btn" @click="goDetail(false)">马上解梦</div>
    </div>
    <div class="main">
      <div class="list-item" v-for="(item, index) in list" :key="index">
        <div class="item-left">
          <img src="/static/images/icon.png" alt="icon">
          <span>{{item.list_title}}</span>
          </div>
        <div class="item-center">
          <span :class="items.highlight ? 'highlight' : ''" v-for="(items, ind) in item.list_item" :key="ind" @click="goDetail(items.content)">
            {{items.content}}
          </span>
        </div>
        <div class="item-right">
          <img src="/static/images/arrow.png" alt="">
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
      list: [
        {
          list_title: '人物',
          list_item: [
            {
              highlight: false,
              content: '双胞胎'
            },
            {
              highlight: false,
              content: '男孩'
            },
            {
              highlight: true,
              content: '娃娃'
            },
            {
              highlight: false,
              content: '伟人'
            },
            {
              highlight: true,
              content: '挂了很多你'
            },
            {
              highlight: false,
              content: '儿子'
            },
            {
              highlight: false,
              content: '儿童'
            },
            {
              highlight: false,
              content: '男友'
            }
          ]
        },
        {
          list_title: '人物',
          list_item: [
            {
              highlight: false,
              content: '双胞胎'
            },
            {
              highlight: false,
              content: '男孩'
            },
            {
              highlight: true,
              content: '娃娃'
            },
            {
              highlight: false,
              content: '伟人'
            },
            {
              highlight: true,
              content: '挂了很多你'
            },
            {
              highlight: false,
              content: '儿子'
            },
            {
              highlight: false,
              content: '儿童'
            },
            {
              highlight: false,
              content: '男友'
            }
          ]
        },
        {
          list_title: '人物',
          list_item: [
            {
              highlight: false,
              content: '双胞胎'
            },
            {
              highlight: false,
              content: '男孩'
            },
            {
              highlight: true,
              content: '娃娃'
            },
            {
              highlight: false,
              content: '伟人'
            },
            {
              highlight: true,
              content: '挂了很多你'
            },
            {
              highlight: false,
              content: '儿子'
            },
            {
              highlight: false,
              content: '儿童'
            },
            {
              highlight: false,
              content: '男友'
            }
          ]
        },
        {
          list_title: '人物',
          list_item: [
            {
              highlight: false,
              content: '双胞胎'
            },
            {
              highlight: false,
              content: '男孩'
            },
            {
              highlight: true,
              content: '娃娃'
            },
            {
              highlight: false,
              content: '伟人'
            },
            {
              highlight: true,
              content: '挂了很多你'
            },
            {
              highlight: false,
              content: '儿子'
            },
            {
              highlight: false,
              content: '儿童'
            },
            {
              highlight: false,
              content: '男友'
            }
          ]
        },
        {
          list_title: '动物',
          list_item: [
            {
              highlight: false,
              content: '老鼠'
            },
            {
              highlight: false,
              content: '老虎'
            },
            {
              highlight: true,
              content: '蛮牛'
            },
            {
              highlight: false,
              content: '野兔'
            },
            {
              highlight: true,
              content: '青龙'
            },
            {
              highlight: false,
              content: '蟒蛇'
            },
            {
              highlight: false,
              content: '千里马'
            },
            {
              highlight: false,
              content: '羊'
            }
          ]
        }
      ],
      motto: 'Hello miniprograme',
      userInfo: {
        nickName: 'mpvue',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  },
  methods: {
    goDetail (query) {
      if (query) this.query = query
      const url = `../detail/main?query=${this.query}`
      console.log(url)
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style lang="scss" scoped>
// 居中样式
// 调取方式 ： @extend .center;
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
.wrapper {
  background: #f7f9fb;
  .header {
    @extend .center;
    border-bottom: 2rpx solid #c3e4f7;
    flex-direction: column;
    .logo {
      margin: 43rpx 0 36rpx 0;
      @extend .center;
      img {
        width: 346rpx;
        height: 118rpx;
      }
    }
    .search-input {
      @extend .center;
      height: 84rpx;
      border: 2px solid #b0deed;
      border-radius: 30px;
      width: 80%;
      font-size: 32rpx;
      span {
        margin-left: 50rpx;
        color: #068bc9;
      }
      input {
        width: 5em;
        //a8afb2
        border: 0;
      }
    }
    .search-btn {
      margin: 43rpx 0 69rpx 0;
      padding: 14rpx 0;
      font-size: 34rpx;
      width: 8em;
      text-align: center;
      text-shadow: 0 1px 085ec2, 1px 0 085ec2, -1px 0 085ec2, 0 -1px 085ec2;
      background: #129cdc;
      color: #d6efff;
      border-radius: 30px;
      box-shadow: 0rpx 5rpx 5rpx 3rpx #57b0da;
    }
  }
  .main {
    .list-item {
      margin-left: 40rpx;
      border-bottom: 1px solid #c1c8d0;
      color: #4c4f51;
      display: flex;
      padding: 32rpx 0;
      .item-left {
        @extend .center;
        flex-direction: column;
        border-radius: 15px;
        width: 100rpx;
        height: 116rpx;
        background: #fff;
        box-shadow: 0rpx 5rpx 5rpx 3rpx #e8e9eb;
        img {
          width: 60rpx;
          height: 54rpx;
        }
        span {
          margin-top: 10rpx;
          font-size: 20rpx;
          color: #616364;
        }
      }
      .item-center {
        flex-wrap: wrap;
        line-height: 58rpx;
        margin-left: 36rpx;
        font-size: 28rpx;
        flex: 1;
        span {
          margin-right: 1em;
        }
        .highlight {
          color: #058bc9;
        }
      }
      .item-right {
        @extend .center;
        width: 95rpx;
        img {
          width: 18rpx;
          height: 34rpx;
        }
      }
    }
  }
}
</style>
