<script>
import foods from './asset/foods/foods.json'

export default {
  data() {
    return {
      message: 'Food List',
      foods: foods
    };
  },
  mounted(){

      console.table(this.foods.length)

  }
};


</script>

<template>


  <h1>{{ message }}</h1>

  <food-item 
    v-for="food in foods"
    :foodName="food.foodName"
    :foodDesc="food.foodDescription"
    :protein="food.protein"
    :calories="food.calories"
    :type="food.foodType"
    v-bind:isFavorite="true"
  />

</template>

<style>

#app > div {
    border: dashed black 1px;
    display: inline-block;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }

  #app > div:hover {
  cursor: pointer;
}


</style>
