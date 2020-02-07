<template>
<div class="container">
  <h1 class="title">Skills</h1>
  <h2 class="subtitle">List is not comprehensive</h2>
  <div class="columns is-multiline">
    <div class="column is-narrow" v-for="skill in skills" v-bind:key="skill.name">
      <div class="card skill-card">
        <header class="card-header">
          <p class="card-header-title">
            <b-taglist attached class="is-large">
              <b-tag> <b-icon v-bind:icon="skill.icon" size="is-medium" v-bind:type="skill.iconType || 'is-success'"/> </b-tag>
              <b-tag v-bind:type="skill.tagType || 'is-success'">{{ skill.name }}</b-tag>
            </b-taglist>
          </p>
        </header>
        <div class="card-content">
          <div class="content">
             <b>Skill: </b>
             <b-icon v-for="index in 5" :key="index"
              v-bind:icon="starsClass(skill.stars, index)"
              size="is-small">
            </b-icon>
            <p>{{skill.description}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import skills from '@/data/skills.yaml'
export default {
  data() {
    // eventually get it parsing local json and yaml files
    return {
      skills
    }
  },
  methods: {
    starsClass: function(numStars, index) {
        return index <= numStars ? 'star' : 'star-outline';
    }
  },
  computed: {
   
  }
}
</script>

<style>
.skill-card {
  width: 250px;
  height: 225px;
  margin: auto;
}
</style>