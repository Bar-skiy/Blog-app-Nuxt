<template>
    <article class="post">
<header class="post-header">
<div class="post-title">
    <h1>Post title</h1>
    <nuxt-link to="/">
        <el-button type="info" plain circle><i class="el-icon-back"></i></el-button>
        
    </nuxt-link>
</div>
<div class="post-info">
    <small>
        <em class="el-icon-time"></em>
        {{ new Date().toLocaleString() }}
    </small>
    <small>
        <em class="el-icon-view"></em>
        21
    </small>
</div>
<div class="post-image">
    <img src="https://a.cdn-hotels.com/gdcs/production50/d44/571ba00b-11cd-4a54-9f2a-5b38da2bc89e.jpg?impolicy=fcrop&w=800&h=533&q=medium"
     alt="post img">
</div>
</header>
<main class="post-content">
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa ad consequuntur incidunt cumque at similique quasi quidem quisquam sit quam. Quia exercitationem iure omnis optio provident recusandae delectus amet aspernatur!</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa ad consequuntur incidunt cumque at similique quasi quidem quisquam sit quam. Quia exercitationem iure omnis optio provident recusandae delectus amet aspernatur!</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa ad consequuntur incidunt cumque at similique quasi quidem quisquam sit quam. Quia exercitationem iure omnis optio provident recusandae delectus amet aspernatur!</p>
</main>
<footer>

</footer>
    </article>
</template>

<script>
export default {
  validate({ params }) {
    return Boolean(params.id);
  },
};
</script>

<style lang="scss" scoped>
.post {
    max-width: 600px;
    margin: 0 auto;
}
.post-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
}
.post-info {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 0.5rem;
}

.post-image img {
    width: 100%;
    height: auto;
}
.post-header {
    margin-bottom: 1.5rem;
}
.post-header {
    margin-bottom: 2rem;
}

</style>