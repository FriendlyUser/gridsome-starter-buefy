<template>
  <div class="post-card content-box" :class="{'post-card--has-poster' : post.poster}">
    <div class="post-card__header">
      <g-image alt="Cover image" v-if="post.coverImage" class="post-card__image" :src="post.coverImage" />
    </div>
    <div class="post-card__content">
      <h2 class="post-card__title" v-html="post.title" />
      <p class="post-card__description" v-html="post.description" />
      <g-link class="post-card__link" :to="post.path">Link</g-link>
    </div>
  </div>
</template>

<script>
// import PostMeta from '~/components/PostMeta'
// import PostTags from '~/components/PostTags'
export default {
  created() {
    console.log(this.post)
    console.log(this.post.coverImage)
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