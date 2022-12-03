<template>
  <el-card shadow="hover" :body-style="{ padding: '0px' }" class="post">
    <header slot="header" class="post-header">
        <h3>Post title</h3>
        <small>
        <em class="el-icon-time"></em>
        {{ new Date().toLocaleString() }}
    </small>
    </header>

    <div>
      <img
        src="https://a.cdn-hotels.com/gdcs/production50/d44/571ba00b-11cd-4a54-9f2a-5b38da2bc89e.jpg?impolicy=fcrop&w=800&h=533&q=medium"
        alt="post img."
        class="post-img"
      />
    </div>

    <footer class="post-footer">
      <el-button round @click="openPost">Open</el-button>
      <span>
        <em class="el-icon-chat-dot-round"></em>
        15
      </span>
    </footer>
  </el-card>
</template>

<script>
export default {
  methods: {
    openPost() {
        const id = 'test-id'
        this.$router.push(`/post/${id}`)
    },
  },
};
</script>

<style lang="scss" scoped>
.post {
    margin-bottom: 1.5rem;
}

.post-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.post-img {
    width: 100%;
    height: auto;
}
.post-footer {
    padding: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>