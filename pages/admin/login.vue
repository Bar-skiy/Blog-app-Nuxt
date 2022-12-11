<template>
  <el-card shadow="always" :style="{width: '500px'}">
    <el-form
      :model="controls"
      :rules="rules"
      ref="form"
      @submit.native.prevent="onSabmit"
    >
      <h1 class="mb1">Login to admin panel</h1>

      <el-form-item label="Login" prop="login">
        <el-input v-model.trim="controls.login"></el-input>
      </el-form-item>

      <div class="mb2">
        <el-form-item label="Password" prop="password">
          <el-input v-model.trim="controls.password" type="password"></el-input>
        </el-form-item>
      </div>

      <el-form-item>
        <el-button type="primary" native-type="submit" :loading="loading">
          Login
        </el-button>
      </el-form-item>
    </el-form>
  </el-card>
</template>

<script>
export default {
  layout: "empty",
  data() {
    return {
      loading: false,
      controls: {
        login: "",
        password: "",
      },
      rules: {
        login: [
          {
            required: true,
            message: "Please input your login",
            trigger: "blur",
          },
        ],
        password: [
          {
            required: true,
            message: "Please input your password",
            trigger: "blur",
          },
          {
            min: 6,
            message: "Password must be at least 6 characters long",
            trigger: "blur",
          },
        ],
      },
    };
  },
  methods: {
    onSabmit() {
this.$refs.form.validate(async valid => {
    if (valid) {
        this.loading = true

        try {
          const formData = {
            login: this.controls.login,
            password: this.controls.password
          }

          await this.$store.dispatch('auth/login', formData)
          this.$router.push('/admin')

        } catch (e) {
            this.loading = false
        }
    }
})

    },
  },
};
</script>