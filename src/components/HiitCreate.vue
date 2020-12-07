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
        <div class="card">
            <div class="card-body">
                <h3 class="card-title">High Intensity Interval</h3>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Name:</span>
                    </div>
                    <input 
                    type="text" 
                    class="form-control" 
                    v-model="timer.highName" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Duration (in seconds):</span>
                    </div>
                    <input 
                    type="number" 
                    class="form-control" 
                    v-model="timer.highDuration" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Color:</span>
                    </div>
                    <select v-model="timer.highColor" class="custom-select">
                        <option v-for="option in timer.colorOptions" v-bind:key="timer.highName + option.text" v-bind:value="option.value">
                            {{option.text}}
                        </option>
                    </select>
            </div>
            </div>
        </div>
        <div class="card">
            <div class="card-body">
                <h3 class="card-title">Low Intensity Interval</h3>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Name:</span>
                    </div>
                    <input 
                    type="text" 
                    class="form-control" 
                    v-model="timer.lowName" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Duration (in seconds):</span>
                    </div>
                    <input 
                    type="number" 
                    class="form-control" 
                    v-model="timer.lowDuration" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Color:</span>
                    </div>
                    <select v-model="timer.lowColor" class="custom-select">
                        <option v-for="option in timer.colorOptions" v-bind:key="timer.lowName + option.text" v-bind:value="option.value">
                            {{option.text}}
                        </option>
                    </select>
                </div>
            </div>
        </div>
        <div class="card">
            <div class="card-body">
                <h3 class="card-title">Warmup</h3>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Name:</span>
                    </div>
                    <input 
                    type="text" 
                    class="form-control" 
                    v-model="timer.warmupName" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Duration (in seconds):</span>
                    </div>
                    <input 
                    type="number" 
                    class="form-control" 
                    v-model="timer.warmupDuration" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Color:</span>
                    </div>
                    <select v-model="timer.warmupColor" class="custom-select">
                        <option v-for="option in timer.colorOptions" v-bind:key="timer.warmupName + option.text" v-bind:value="option.value">
                            {{option.text}}
                        </option>
                    </select>
                </div>
            </div>
        </div>
        <div class="card">
            <div class="card-body">
                <h3 class="card-title">Cooldown</h3>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Name:</span>
                    </div>
                    <input 
                    type="text" 
                    class="form-control" 
                    v-model="timer.cooldownName" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Duration (in seconds):</span>
                    </div>
                    <input 
                    type="number" 
                    class="form-control" 
                    v-model="timer.cooldownDuration" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Color:</span>
                    </div>
                    <select v-model="timer.cooldownColor" class="custom-select">
                        <option v-for="option in timer.colorOptions" v-bind:key="timer.cooldownName + option.text" v-bind:value="option.value">
                            {{option.text}}
                        </option>
                    </select>
                </div>
            </div>
        </div>
        <div class="fixed-bottom bg-light">
            <div class="row">
                <div class="col-lg-12">
                    <button class="btn btn-outline-success float-right margin-right20" type="button">Create</button>
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
    

    timer = { 
        name:'HIIT Timer',
        numberOfSets: 6,
        
        highName: 'High Intensity',
        highDuration: 30,
        highColor: 'red',
        
        lowName: 'Low Intensity',
        lowDuration: 30,
        lowColor: 'green',

        warmupName: 'Warmup',
        warmupDuration: 180,
        warmupColor: 'yellow',

        cooldownName: 'Cooldown',
        cooldownDuration: 180,
        cooldownColor: 'yellow',
        colorOptions: [
            {text: 'Green', value: 'green'},
            {text: "Red", value: 'red'},
            {text: 'Yellow', value: 'yellow'},
            {text: 'Magenta', value:'rgb(230, 46, 95)'},
            {text: 'Deep purple', value:'rgb(133, 57, 191)'}
        ]
    };

    setup () {
        return {
            
        }
    }
}
</script>

<style scoped>
.card {
    margin-bottom: 20px;
}
.margin-right20{
    margin-right: 20px;
}
</style>