<template>
  <Layout>
    <div class="container">
        <div class="level">
            <div class="level-left">
                <strong>Time To Read:</strong> &nbsp;
                <span> {{$page.post.timeToRead}} minute</span>
            </div>
            <div class="level-right">
                <h1 class="title is-3">{{$page.post.title}}</h1>
            </div>
        </div>
        <g-image
            v-if="$page.post.image" 
            :src="$page.post.image" alt="Placeholder image" 
            width="100%" fit="fill"
        />
        <div id="content" v-html="$page.post.content" />
    </div>
  </Layout>
</template>

<page-query>
query blogPost ($path: String!) {
  post: blogPost (path: $path) {
    title
    path
    timeToRead
    content
    image
  }
}
</page-query>


<style>
#content .img {
  max-width: 50%;
}
</style>
<script>
export default {
  metaInfo () {
    return {
      title: this.$page.post.title
    }
  }
}
</script>
