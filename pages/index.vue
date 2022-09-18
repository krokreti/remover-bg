<template >
  <div class="h-screen bg-gradient-to-b from-black to-gray-800">
    <Home />
  </div>
</template>

<script>
import Home from '~/components/Home.vue'

export default {
  name: 'IndexPage',
  components : {
    Home,
  }
}
</script>
