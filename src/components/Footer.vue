<template>
    <div>
        <footer>
            <p>{{mydate}}</p>
            
        </footer>
    </div>
</template>

<script>
    export default {
        name:'Footer',
        data(){
            return {
                mydate:new Date().toLocaleString()
            }
        }
    }
</script>

<style scoped>

a{
    color:#333;
}

footer {
    margin-top:30px;
    text-align: center;
}

</style>