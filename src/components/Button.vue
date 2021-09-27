<template>
    <div>
        <button @click="onClick()"  class="btn" :style="{background:color}">{{text}}</button>
    </div>
</template>

<script>
    export default {
        name:'Button',
        props:{
            text:String,
            color:String
        },
        methods:{
            onClick(){
              this.$emit('btn-clk') 
            }
        },
        emits:['show-add-task']
    }
</script>

<style scoped>

</style>