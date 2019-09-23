<template>
<Layout title="Project">
  <div class="container">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          {{$page.githubProject.name}}
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <b-icon
            icon="account"
            size="is-small">
          </b-icon>
        </a>
      </header>
      <div class="card-content">
        <div class="content">
          <br>
          <div v-html="$page.githubProject.contents">
          </div>
          <!-- <time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time> -->
          <!-- <button class="button is-dark">
            <b-icon icon="check"></b-icon>
            <span>Finish</span>
          </button> -->
        </div>
      </div>
      <footer class="card-footer">
        <a href="#" class="card-footer-item">{{$page.githubProject.created_at}}</a>
        <a href="#" class="card-footer-item">{{$page.githubProject.language}}</a>
        <a href="#" class="card-footer-item">{{$page.githubProject.data.stargazers_count}}</a>
      </footer>
    </div>
  </div>
</Layout>
</template>


<page-query>
query githubProject ($path: String!) {
  githubProject: githubProject (path: $path) {
    id
    html_url
    created_at
    forks
    name
    contents
    language
    data {
      language
      forks
      stargazers_count
    }
  }
}
</page-query>

<script>
import Layout from '~/layouts/Default'
export default {
  components: {
    Layout
  },
  metaInfo () {
    return {
      title: this.$page.githubProject.title
    }
  }
}
</script>
