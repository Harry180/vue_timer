<template>
    <nav class="navbar navbar-expand-md navbar-dark bg-dark fixed-top">
      <div class="collapse navbar-collapse" id="navbarsExampleDefault">
        <router-link to="/">Home</router-link>
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