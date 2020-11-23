<template>
    <div class="starter-template">
        <h1>{{ title }}</h1>
        <div class="panel">
            <div class="panel-heading">
                <h3 class="panel-title">Timer Details</h3>
            </div>
            <div class="panel-body">
                <div class="form-group">
                    <label for="name">Name: </label>
                    <input v-model="timer.name" type="text" />
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">

import { Component, Prop, Vue } from 'vue-property-decorator';
@Component
export default class HiitCreate extends Vue {
    @Prop() private title!: string;
    timer = {name:''};

    setup () {
        return {
            
        }
    }
}
</script>

<style scoped>

</style>