<template>
  <div class="post-card content-box" :class="{'post-card--has-poster' : post.poster}">
    <div class="post-card__header">
      <g-image alt="Cover image" v-if="post.coverImage" class="post-card__image" :src="post.coverImage" />
    </div>
    <div class="post-card__content">
      <h2 class="post-card__title" v-html="post.title" />
      <p class="post-card__description" v-html="this.excerpt" />
      <g-link class="post-card__link" :to="post.path">Link</g-link>
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