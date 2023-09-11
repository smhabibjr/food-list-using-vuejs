<template>
    <div v-on:click="clicksCounter">
        <h1> {{ foodName }} <img v-show="foodIsFavorite" style="height: 30px;width: 30px;" src="../asset/images/img_quality.png" alt=""> </h1>

        <p> <span style="font-weight: bold;">Description : </span> {{ foodDesc }}</p>

        <p style="border: solid 1px black; padding: 10px;"> Food Type : {{ foodType }} , Protein: {{ foodProtein }} g, calories: {{ foodCalorie }}  </p>
        <p>You have clicked this element {{ clicks }} times. </p>
        <p> {{ foodName }} is your favorite food? <input v-model="foodIsFavorite" type="checkbox"> </p>
    </div>


</template>

<script>
    export default {
        props: {
            foodName: {
                type: String,
                required: true
            },
            foodDesc: {
                type: String,
                required: false,
                default: 'This is a default desc',
                validator: function(value){
                    if(value.length > 20 ){
                        return true
                    }else{
                        return false
                    }
                    console.log(value);
                }
            },
            isFavorite: {
                type: Boolean,
                required: false,
                default: false
            },
            type:{
                type: String,
                default: 'Food',
                required: false
            },
            protein:{
                type:Number,
                required: true
            },
            calories: {
                type: Number,
                required: true
            }
        },
        data(){
            return{
                name: this.foodName,
                description: this.foodDesc,
                foodType: this.type,
                foodProtein: this.protein,
                foodCalorie: this.calories,
                clicks: 0,
                foodIsFavorite: this.isFavorite
            }
        },
        methods: {
            clicksCounter(){
                this.clicks++;
            }
        }
    }
</script>

<style>

</style>