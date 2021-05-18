<template>
    <header>
        <h1>{{title}}</h1>
        
        <Button @btn-click="$emit('toggle-add-task')" :text="showAddTask ?  'Close' : 'Add Task'" :color="showAddTask ? 'tomato' : 'pink'"/>
    </header>
</template>
<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean
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