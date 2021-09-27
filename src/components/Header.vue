<template>
    <header>
        <h1>{{title}}</h1>
        <Button @show-add-task="$emit('show-add-task')" text="Add Task" color="green"/>
        <!-- <Button text="Update Task" color="gray"/>
        <Button text="Delete Task" color="red"/> -->

    </header>
</template>

<script>
import Button from './Button.vue'
    export default {
        name:'Header',
        props:{
            title:{
                type:String,
                default:'Hello'
            }
        },
        components:{
            Button
        },
        emits:['show-add-task']
    }
</script>

<style scoped>
    header {
        display:flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>