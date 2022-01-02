<template>
  <div class="login_container">
    <!-- 登录块 -->
    <div class="login_box">
      <div class="avatar_box">
        <img src="../assets/logo.png" />
      </div>
      <!-- 表单区域  -->
      <el-form
        ref="loginForm"
        :model="loginForm"
        :rules="loginRules"
        class="login_form"
        label-width="0"
      >
        <!-- 用户名 -->
        <el-form-item prop="username">
          <el-input
            v-model="loginForm.username"
            prefix-icon="iconfont icon-denglu"
          ></el-input>
        </el-form-item>
        <!-- 密码 -->
        <el-form-item prop="password">
          <el-input
            v-model="loginForm.password"
            prefix-icon="iconfont icon-mima1"
          ></el-input>
        </el-form-item>
        <!-- 按钮 -->
        <el-form-item class="btns">
          <el-button type="primary">提交</el-button>
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
      // 表单数据
      loginForm: {
        username: "username",
        password: "password",
      },
      // 验证对象
      loginRules: {
        // 校验用户名
        username: [
          { required: true, message: '请输入用户名', trigger: 'blur'},//必填项验证，blur表示触发方式为失去焦点。（trigger，触发）
          { min: 5, max: 12, message: '长度在 5 到 12 个字符', trigger: 'blur' },//长度验证
        ],
        // 校验密码
        password: [
          { required: true, message: '请输入密码', trigger: 'blur'},//必填项验证，blur表示失去焦点
          { min: 6, max: 10, message: '长度在 6 到 10 个字符', trigger: 'blur' },//长度验证

        ]
      }
    };
  },
};
</script>

<style  scoped>
.login_container {
  background-color: #2b4b6b;
  height: 100%;
}
.login_box {
  width: 450px;
  height: 300px;
  background-color: #fff;
  border-radius: 3px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
.avatar_box {
    width: 130px;
    height: 130px;
    border: 1px solid #eee;
    border-radius: 50%;
    padding: 5px;
    box-shadow: 0 0 5px #ddd;
    position: absolute;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #0ee;

}
img {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background-color: #eee;
}
.btns {
    display: flex;
    justify-content: flex-end;

}
.login_form {
    position: absolute;
    bottom: 0%;
    width: 100%;
    padding: 0 10px;
    box-sizing: border-box;
}

</style>