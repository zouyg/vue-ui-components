<template>
    <div id="app">
        <img src="./assets/logo.png">
        <g-buton>欢迎使用轱辘</g-buton>
    </div>
</template>

<script>
    import HellloWorld from './components/HelloWorld.vue'
    import {Button, ButtonGroup, Icon} from 'gulu-zouyg-1'
    import 'gulu-zouyg-1/dist/index.css'
    export default {
        name: "App",
        components: {
            HelloWorld,
            'g-button': Button,
            'g-icon': Icon
        }
    }
</script>

<style>
    html {
        --button-height: 32px;
        --font-size: 14px;
        --button-bg: white;
        --button-active-bg: #eee;
        --border-radius: 4px;
        --color: #333;
        --border-color: #999;
        --border-color-hover: #666;
    }
</style>