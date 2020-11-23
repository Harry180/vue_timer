<template>
    <nav>      
      <router-link to="/">Home</router-link>
    </nav>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class NavBar extends Vue{
    setup () {
        

        return {}
    }
}
</script>

<style scoped>

</style>