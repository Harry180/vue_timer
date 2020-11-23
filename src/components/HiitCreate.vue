<template>
    <div class="container-fluid">
        <h1>{{ title }}</h1>
        <div class="card">
            <div class="card-body">
            <h3 class="card-title">Timer Details</h3>
            <div class="input-group">
                <div class="input-group-prepend">
                    <span class="input-group-text">Name:</span>
                </div>
                <input 
                type="text" 
                class="form-control" 
                v-model="timer.name" />
            </div>
            <div class="input-group">
                <div class="input-group-prepend">
                    <span class="input-group-text">Number Of Sets:</span>
                </div>
                <input 
                type="number" 
                class="form-control" 
                v-model="timer.numberOfSets" />
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