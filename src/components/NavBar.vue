<template>
    <nav class="navbar navbar-dark bg-dark">
      <div class="navbar-brand" id="navbarsExampleDefault">
        <router-link class="nav-item" to="/">Home</router-link>
      </div>  
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