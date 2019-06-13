<template>
  <div class="wrapper">
    <div class="header">
      <img src="/static/images/header.png"/>
      <!-- <input type="text" placeholder="哈哈哈"> -->
    </div>
    <div class="main">
      <div class="list-item" v-for="(item, index) in list" :key="index">
        <div class="item-left">-{{item.list_title}}-</div>
        <div class="item-center">
          <span :class="items.highlight ? 'highlight' : ''" v-for="(items, ind) in item.list_item" :key="ind">
            {{items.content}}
          </span>
        </div>
        <div class="item-right"> > </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
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
              content: '挂了很多'
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
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style lang="scss" scoped>
body {
  background: #f7f9fb;
}
.wrapper {
  .header {
    img {
      width: 100%;
    }
  }
  .main {
    .list-item {
      border-bottom: 1px solid #c1c8d0;
      color: #4c4f51;
      display: flex;
      .item-left {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 80px;
        background: #fff;
      }
      .item-center {
        flex: 1;
        .highlight {
          color: #058bc9;
        }
      }
      .item-right {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 30px;
      }
    }
  }
}
</style>
