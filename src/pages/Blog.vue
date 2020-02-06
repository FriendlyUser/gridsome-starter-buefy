<template>
  <Layout :show-logo="false">

    <!-- List posts -->
    <div class="container">
      <div class="columns">
        <div class ="column is-third" v-for="edge in $page.posts.edges" :key="edge.node.id">
          <!-- content -->
          <BlogPostCard :key="edge.node.id" :post="edge.node"/>
        </div>
      </div>
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