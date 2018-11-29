<template>
  <div>
    <div class="header">
      <div class="search" @click="navigate('/pages/index/search/main')">
        <span>搜索特色理疗/营养餐</span>
      </div>
      <div class="temperature" @click="addNumber()">
        温度{{ number }}
      </div>
    </div>
    <div class="lists">
      <div>
        <img src="/static/images/home_ic_doctor.png" alt="">
        <div>在线问诊</div>
      </div>
      <div>
        <img src="/static/images/home_ic_cure.png" alt="">
        <div>特色理疗</div>
      </div>
      <div>
        <img src="/static/images/home_ic_meal.png" alt="">
        <div>营养餐</div>
      </div>
      <div @click="navigate('/pages/party/main', 'switch')">
        <img src="/static/images/home_ic_party.png" alt="">
        <div>院内党建</div>
      </div>
    </div>
  </div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
      number: 1,
      userInfo: {}
    }
  },

  components: {
    card
  },

  methods: {
    navigate (url, swi) {
      if (swi) {
        wx.switchTab({ url })
      } else {
        wx.navigateTo({ url })
      }
    },
    addNumber() {
      console.log(this.number);
      this.number++
    }
  },

  created () {
    // 调用应用实例的方法获取全局数据
  }
}
</script>

<style lang="scss" scoped>
  .header {
    background: url(https://lg-kj9oazyk-1255424980.cos.ap-shanghai.myqcloud.com/home_bg_today.png) no-repeat center scroll;
    background-size: 100% 100%;
    height: 150px;
    text-align: center;
    padding-top: 10px;
    .search {
      width: 80%;
      margin-left: 10%;
      background: #fff;
      border-radius: 20px;
      border: 1px solid #999;
      font-size: 14px;
      padding: 8px 0;
      text-align: center;
      color: #36cdb6;
    }
    .temperature {
      padding: 20px 0;
    }
  }
  .lists {
    margin-top: 10px;
    > div {
      width: 25%;
      display: inline-block;
      font-size: 14px;
      text-align: center;
      img {
        width: 50px;
        height: 50px;
      }
    }
  }
</style>
