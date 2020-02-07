<template>
  <Layout :show-logo="false">
    <br />
    <!-- List posts -->
    <div class="container">
      <h4 class="subtitle is-3">Latest Blog Posts</h4>
      <br />
      <div class="columns is-multiline">
        <!-- content -->
        <div class="column is-one-third" v-for="edge in $page.posts.edges" :key="edge.node.id">
          <BlogPostCard :key="edge.node.id" :post="edge.node"/>
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query {
  posts: allBlogPost(limit: 12) {
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