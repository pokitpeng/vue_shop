<template>
  <div class="login_container">
    <div class="login_box">
      <!-- 头像区域 -->
      <div class="logo_box">
        <img src="../assets/logo.png" alt="" />
      </div>

      <!-- 登陆表单区域 -->
      <el-form :model="loginForm" :rules="loginFromRules" label-width="0px" class="login_form">
        <!-- 用户名 -->
        <el-form-item prop="username">
          <el-input v-model="loginForm.username" prefix-icon="el-icon-user"></el-input>
        </el-form-item>
        <!-- 密码 -->
        <el-form-item prop="password">
          <el-input v-model="loginForm.password" prefix-icon="el-icon-key" type="password"></el-input>
        </el-form-item>

        <!-- 按钮 -->
        <el-form-item class="btn">
          <el-button type="primary">登陆</el-button>
          <el-button type="info">重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // 这是登陆表单的数据模板对象
      // 1. 在登陆表单中添加绑定对象 :model="loginForm"
      // 2. 在表单输入区域绑定对象对应的属性  v-model="loginForm.username"
      loginForm: {
        username: "admin",
        password: "123456",
      },
      // 表单数据校验
      // 1. 在登陆表单中添加登陆校验对象 :rules="loginFromRules"
      // 2. 添加验证规则
      // 3. 在输入表单中绑定规则 prop="username"
      loginFromRules: {
        // 验证用户名是否合法，格式为数组，可添加多条规则
        username: [
          { required: true, message: "请输入用户名", trigger: "blur" },
          {
            min: 3,
            max: 20,
            message: "长度在 3 到 20 个字符",
            trigger: "blur",
          },
        ],
        // 验证密码是否合法
        password: [
          { required: true, message: "请输入密码", trigger: "blur" },
          {
            min: 6,
            max: 20,
            message: "长度在 6 到 20 个字符",
            trigger: "blur",
          },
        ],
      },
    };
  },
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
.login_form {
  position: absolute;
  bottom: 0; // 放在底部边缘
  width: 100%;
  padding: 0 20px;
  box-sizing: border-box; // 长度不超过边缘
}
.btn {
  display: flex; // 按钮框转成弹性盒模型
  justify-content: flex-end; // 右对齐
  // position: absolute;
  // left: 50%; // 右移50%
}
</style>