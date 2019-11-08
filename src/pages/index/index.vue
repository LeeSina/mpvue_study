<template>
  <div class="indexContainer">
    <img class="index_img" src="../../../static/images/user.png" alt="">
    <p class="userName">hello world</p>
    <div class="goStudy">
      <p>开启小程序之旅</p>
    </div>
  </div>
</template>

<script>
  export default {

    onLoad () {
      console.log("---onLoad----");
    },
    beforeMount () {
      console.log("---beforeMount----");

      // 获取用户登录信息
      wx.getUserInfo({
        // 成功回调
        success: (data) => {
          console.log(data)
        },
        fail: () => {
          console.log("获取失败");
        }
      });
    },
    mounted () {
      console.log("---mounted----");
    }
  };
</script>

<style>

  /*page {*/
  /*background: #E3544C;*/
  /*}*/

  .indexContainer {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .index_img {
    width: 200rpx;
    height: 200rpx;
    margin: 100rpx 0;
  }

  .userName {
    font-size: 40rpx;
    font-weight: bold;
    margin: 100rpx 0;
  }

  .goStudy {
    width: 220rpx;
    height: 80rpx;
    border: 1rpx solid #eee;
    font-size: 24rpx;
    line-height: 80rpx;
    text-align: center;
    border-radius: 10rpx;
  }

  
</style>
