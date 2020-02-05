<template>
  <Layout :show-logo="false">

    <!-- List posts -->
    <div class="posts">
      <BlogPostCard v-for="edge in $page.posts.edges" :key="edge.node.id" :post="edge.node"/>
    </div>

  </Layout>
</template>

<page-query>
query {
  posts: allBlogPost {
    edges {
      node {
        id
        title
        timeToRead
        path
        image
        excerpt
        description
        content
      }
    }
  }
}
</page-query>

<script>
// maps to /blog
import BlogPostCard from '~/components/BlogPostCard.vue'
export default {
  data() {
    console.log(this)
    return {}
  },
  components: {
    // Author,
    BlogPostCard
  },
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>