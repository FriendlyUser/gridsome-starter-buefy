<template>
<Layout title="David Li Portfolio">
  <br />
  <br />
  <Skills />
  <br />
  <div class="container">
    <h1 class="title">Gridsome</h1>
    <h2 class="subtitle">Steps to get started</h2>
  </div>
  <hr />
  <br />
  <div class="container">
  <b-steps
     v-model="activeStep"
    :animated="isAnimated"
    :has-navigation="hasNavigation"
    :icon-prev="prevIcon"
    :icon-next="nextIcon"
  >
    <b-step-item label="Installation" icon="npm">
      <ul>
        <li> Install gridsome by running <i> npm install -g gridsome </i> </li>
        <li> Then clone this repo by running <i> git clone TODO ADD REPO NAME</i> </li>
      </ul>
    </b-step-item>
    <b-step-item label="Configuration" icon="web">
      <ul>
        <li> Update <i>gridsome.config.js</i> with unique site name and hosting details. </li>
        <li> Change formspree to use your personal email address. </li>
      </ul>
    </b-step-item>
    <b-step-item label="Deployment" icon="azure">
      Deployment can be handled using azure pipelines, additionally considering adding more customization.
    </b-step-item>
  </b-steps>
  </div>
  <div class="container">
    <h3 class="title">Contact Me</h3>
    <section>
      <form action="https://formspree.io/davidli012345@gmail.com" method="POST">
        <b-field horizontal label="Subject" type="is-danger" message="Please enter a subject">
          <b-input name="subject" expanded></b-input>
        </b-field>

        <b-field horizontal label="From">
          <b-input name="name" placeholder="Name" expanded></b-input>
          <b-input name="email" type="email" placeholder="nobody@nowhere.com" expanded></b-input>
        </b-field>

        <b-field horizontal label="Topic">
          <b-select placeholder="Select a topic">
            <option value="1">Bulma</option>
            <option value="2">Vue.js</option>
            <option value="3">Buefy</option>
          </b-select>
        </b-field>

        <b-field horizontal label="Message">
          <b-input type="textarea" name="text"></b-input>
        </b-field>

        <b-field horizontal><!-- Label left empty for spacing -->
          <p class="control">
            <button class="button is-primary">
              Send message
            </button>
          </p>
        </b-field>
      </form>
    </section>
  </div>
  <footer class="footer">
  <div class="content has-text-centered">
    <p>
      <strong>Gridsome Starter Buefy</strong> by <a href="https://FriendlyUser.github.io">David Li</a>. The source code is licensed
      <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. The website content
      is licensed <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY NC SA 4.0</a>.
    </p>
  </div>
</footer>
</Layout>
</template>

<script>
import Skills from '~/components/Skills'
import Layout from '~/layouts/Default.vue'
export default {
  components: {
    Layout,
    Skills
  }
}
</script>

<style>
</style>