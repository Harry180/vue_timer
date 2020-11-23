<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HiitCreate title="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HiitCreate from '@/components/HiitCreate.vue'

export default {
  name: 'Home',
  components: {
    HiitCreate
  }
}
</script>
