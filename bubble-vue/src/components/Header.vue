<template>
    <header>
        <h1>{{title}}</h1>
        
        <Button text="Add Task" color="pink"/>
    </header>
</template>
<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: String,
    },
    components: {
        Button
    }
}
</script>
<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
        background-color: rgb(73, 168, 168);
        border-radius: 80px;
        padding: 10px;
        color: white;
    }
    
    h1 {
        margin-left: 20px;
    }
</style>