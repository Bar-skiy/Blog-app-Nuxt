<template>
  <el-form
    :model="controls"
    :rules="rules"
    ref="form"
    @submit.native.prevent="onSabmit"
  >
    <h1>Add a comment</h1>
    <el-form-item label="Activity name" prop="name">
      <el-input v-model.trim="controls.name"></el-input>
    </el-form-item>

    <el-form-item label="Comment text" prop="text">
      <el-input
        type="textarea"
        v-model.trim="controls.text"
        resize="none"
        :rows="2"
      ></el-input>
    </el-form-item>

    <el-form-item>
      <el-button type="primary" native-type="submit"> Add comment </el-button>
    </el-form-item>
  </el-form>
</template>

<script>
export default {
  data() {
    return {
      controls: {
        name: "",
        text: "",
      },
      rules: {
        name: [
          {
            required: true,
            message: "Please input Activity name",
            trigger: "blur",
          },
        ],
        text: [
          {
            required: true,
            message: "Please input comment",
            trigger: "blur",
          },
        ],
      },
    };
  },
  methods: {
    onSabmit() {
      this.$refs.form.validate((valid) => {
        if (valid) {
          console.log("form is valid");
        }
      });
    },
  },
};
</script>

<style lang="scss" scoped>
</style>