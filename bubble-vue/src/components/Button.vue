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
            this.$emit('btn-click')
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
        color: rgb(253, 252, 223);
        margin: 20px;
        
    }
</style>