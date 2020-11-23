<template>
    <div>
        <h1>{{ title }}</h1>
    </div>
</template>

<script lang="ts">

import { Component, Prop, Vue } from 'vue-property-decorator';
@Component
export default class HiitCreate extends Vue {
    @Prop() private title!: string;
    setup () {
        return {}
    }
}
</script>

<style scoped>

</style>