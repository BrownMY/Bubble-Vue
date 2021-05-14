<template>
    <button @click="onClick()" :style="{ background: color }" class="btn">{{text}}</button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: String,
        color: String
    },
    methods: {
        onClick() {
            console.log('Clciekd!')
        }
    }
}
</script>
<style scoped>
    button {
        border: none;
        border-radius: 10px;
        padding: 10px;
        font-size: 20px;
        color: rgb(221, 90, 167);
        margin: 20px;
        
    }
</style>