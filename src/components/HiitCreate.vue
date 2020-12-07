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
                    v-model="timer.high.name" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Duration (in seconds):</span>
                    </div>
                    <input 
                    type="number" 
                    class="form-control" 
                    v-model="timer.high.duration" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Color:</span>
                    </div>
                    <select v-model="timer.high.color" class="custom-select">
                        <option v-for="option in timer.colorOptions" v-bind:key="timer.high.name + option.text" v-bind:value="option.value">
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
                    v-model="timer.low.name" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Duration (in seconds):</span>
                    </div>
                    <input 
                    type="number" 
                    class="form-control" 
                    v-model="timer.low.duration" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Color:</span>
                    </div>
                    <select v-model="timer.low.color" class="custom-select">
                        <option v-for="option in timer.colorOptions" v-bind:key="timer.low.name + option.text" v-bind:value="option.value">
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
                    v-model="timer.warmup.name" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Duration (in seconds):</span>
                    </div>
                    <input 
                    type="number" 
                    class="form-control" 
                    v-model="timer.warmup.duration" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Color:</span>
                    </div>
                    <select v-model="timer.warmup.color" class="custom-select">
                        <option v-for="option in timer.colorOptions" v-bind:key="timer.warmup.name + option.text" v-bind:value="option.value">
                            {{option.text}}
                        </option>
                    </select>
                </div>
            </div>
        </div>
        <div class="card mb-5">
            <div class="card-body">
                <h3 class="card-title">Cooldown</h3>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Name:</span>
                    </div>
                    <input 
                    type="text" 
                    class="form-control" 
                    v-model="timer.cooldown.name" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Duration (in seconds):</span>
                    </div>
                    <input 
                    type="number" 
                    class="form-control" 
                    v-model="timer.cooldown.duration" />
                </div>
                <div class="input-group">
                    <div class="input-group-prepend">
                        <span class="input-group-text">Color:</span>
                    </div>
                    <select v-model="timer.cooldown.color" class="custom-select">
                        <option v-for="option in timer.colorOptions" v-bind:key="timer.cooldown.name + option.text" v-bind:value="option.value">
                            {{option.text}}
                        </option>
                    </select>
                </div>
            </div>
        </div>
        <div class="fixed-bottom bg-light">
            <div class="row">
                <div class="col-sm-12 col-md-10">
                    <ul class="preview-list">
                        <li class="preview-list-item" v-for="index in timer.numberOfSets" :key="index" :style="{backgroundColor: timer.warmupColor}">&nbsp;</li>
                    </ul>
                </div>
                <div class="col-sm-12 col-md-2">
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
        
        high:{
            name: 'High Intensity',
            duration: 30,
            color: 'red',
        },
        low: {
            name: 'Low Intensity',
            duration: 30,
            color: 'green'
        },
        
        warmup: {
            name: 'Warmup',
            duration: 180,
            color: 'yellow'
        },
        
        cooldown: {
            name: 'Cooldown',
            duration: 180,
            color: 'yellow'
        },
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
.preview-list {
    border-radius: 4px;
    margin: 0 0 15px;
    padding: 0;
    list-style-type: none;
}
.preview-list-item{
    display: inline-block;
    height: 34px;
    text-indent: -9999px;
    border-right: 1px solid #fff;
    width: 10px;
}
</style>