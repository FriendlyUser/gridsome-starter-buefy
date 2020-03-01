<template>
  <div class="card">
    <div class="card-image">
      <figure class="image is-4by3 image-container">
        <g-link :to="post.path">
          <g-image v-if="post.image" :src="post.image" alt="Placeholder image" />
        </g-link>
      </figure>
    </div>
    <div class="card-content">
      <div class="media">
        <div class="media-left">
          <figure class="image is-48x48 image-container-ii">
            <g-image v-if="post.image" :src="post.image" alt="Placeholder image" />
          </figure>
        </div>
        <div class="media-content">
          <p class="title is-4">{{post.title}}</p>
          <p class="subtitle is-6">{{post.title}}</p>
        </div>
      </div>
      <div class="content" v-html="this.excerpt" />
      <g-link :to="post.path">Link</g-link>
      <br />
      <time datetime="2016-1-1">{{post.date}}</time>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      excerpt: this.generateExcerpt(this.post.content, 290)
    }
  },
  methods: {
    generateExcerpt: function(textToStrip, length) {
      // remove tags
      // let regex = /(<([^>]+)>)/gi
      return textToStrip.slice(0,length)
    }
  },
  created() {
  },
  components: {
  },
  props: ['post'],
}
</script>

<style>

.image-container-ii:before {
  content: " ";
  position: absolute;
  top: 50%;
  left: 50%;
  max-width: 100%;
  max-height: 100%;
  width: 80px;
  height: 80px;
  border: 2px solid #f3f3f3;
  border-radius: 50%;
  border-top: 2px solid blue;
  border-right: 2px solid blue;
  border-bottom: 2px solid blue;
  /** border-color: transparent red transparent red; */
  animation: loader 1s linear infinite;
}
.image-container-ii > img {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100% !important;
  height: 100% !important;
}

/** See https://stackoverflow.com/questions/45018456/displaying-loading-image-using-css */
.image-container:before {
  content: " ";
  position: absolute;
  top: 50%;
  left: 50%;
  max-width: 100%;
  max-height: 100%;
  width: 80px;
  height: 80px;
  border: 2px solid #f3f3f3;
  border-radius: 50%;
  border-top: 2px solid blue;
  border-bottom: 2px solid blue;
  /** border-color: transparent red transparent red; */
  animation: loader 1s linear infinite;
}
.image-container > img {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100% !important;
  height: 100% !important;
}
@keyframes loader {
  0% {
    transform: translate(-50%,-50%) rotate(0deg);
  }
  100% {
    transform: translate(-50%,-50%) rotate(360deg);
  }
}
</style>
