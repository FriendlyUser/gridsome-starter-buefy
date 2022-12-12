<template>
<div>
  <Navbar />
  <Adsense
      data-ad-client="ca-pub-2479144310234386"
      data-ad-slot="1234567890">
  </Adsense>
  <transition name="fade" appear>
    <main> <!-- a wrapper for slot is needed -->
      <slot /> <!-- the content -->
    </main>
  </transition>
</div>
</template>

<script>
import Navbar from '~/components/Navbar'
export default {
  components: {
    Navbar
  }
}
</script>

<style>
.fade-enter-active {
  transition: opacity .5s;
}

.fade-enter {
  opacity: 0;
}
</style>