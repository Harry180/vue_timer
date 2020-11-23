<template>
  <div class="home">
    <HiitCreate title="Welcome to HIIT timer app by charubiniak.pl"/>
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
