<template>
  <div class="login_container">
    <div class="login_box">
      <div class="logo_box">
        <img src="../assets/logo.png" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // 下面可不写
  // name: "Login",
  // props: {
  //   msg: String,
  // },
};
</script>


<style lang="less" scoped>
// less表示当组件支持less语法
// scoped表示样式只在当前组件生效

.login_container {
  background-color: #2b4b6b;
  height: 100%;
}

.login_box {
  width: 450px;
  height: 300px;
  background-color: white;
  border-radius: 10px; // 圆角边框
  position: absolute; // 绝对定位
  left: 50%; // 左边50%
  top: 50%; // 上边50%
  transform: translate(-50%, -50%); // 横轴移动-50%，纵轴上移动-50%
}
.logo_box {
  height: 130px;
  width: 130px;
  border: 5px, solid, #eee; // 盒子边框
  padding: 10px; // 内边距
  border-radius: 50%; // 圆角
  box-shadow: 1px 1px 10px #eee; // 盒子外边阴影 （右移 下移 羽化范围 颜色）
  position: absolute; // 相对最近的盒子绝对定位
  left: 50%; // 右移50%
  transform: translate(-50%, -50%); // 横轴移动-50%，纵轴上移动-50%
  background-color: #eee;
  // 图片嵌在盒子里面
  img {
    width: 100%;
    height: 100%;
    border-radius: 50%; // 图片超出了盒子范围，所以图片也要调整圆角
  }
}
</style>