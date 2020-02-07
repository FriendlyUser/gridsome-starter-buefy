<template>
  <div class="card">
    <div class="card-image">
      <figure class="image is-4by3">
        <a :href="post.path">
          <g-image v-if="post.image" :src="post.image" alt="Placeholder image" />
        </a>
      </figure>
    </div>
    <div class="card-content">
      <div class="media">
        <div class="media-left">
          <figure class="image is-48x48">
            <g-image v-if="post.image" :src="post.image" alt="Placeholder image" />
          </figure>
        </div>
        <div class="media-content">
          <p class="title is-4">{{post.title}}</p>
          <p class="subtitle is-6">{{post.title}}</p>
        </div>
      </div>
      <div class="content" v-html="this.excerpt" />
      <g-link :href="post.path" :to="post.path">Link</g-link>
      <br />
      <time datetime="2016-1-1">{{post.date}}</time>
    </div>
  </div>
</template>

<script>
// import PostMeta from '~/components/PostMeta'
// import PostTags from '~/components/PostTags'
export default {
  data() {
    return {
      excerpt: this.generateExcerpt(this.post.content, 290)
    }
  },
  methods: {
    generateExcerpt: function(textToStrip, length) {
      // let regex = /(<([^>]+)>)/gi
      return textToStrip.slice(0,length)
    }
  },
  created() {
  },
  components: {
    // PostMeta,
    // PostTags
  },
  props: ['post'],
}
</script>

<style>
</style>