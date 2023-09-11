<template>
    <div v-on:click="clicksCounter">
        <h1> {{ name }} </h1>
        <p>{{ para }}</p>
        <p>You have clickec me {{ clicks }} </p>
    </div>


</template>

<script>
    export default {
        data(){
            return{
                name: 'Apples',
                message: 'I like apples',
                clicks: 0
            }
        },
        methods: {
            clicksCounter(event){
                this.clicks++;
            }
        }
    }
</script>

<style>

</style>