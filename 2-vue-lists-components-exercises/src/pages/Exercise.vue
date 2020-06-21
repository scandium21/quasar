<template>
  <!--
	Awesome Exercise 2 - Vue.js Lists & Components

	1) Create an array for the food items you see on the page. Each object in the array should contain properties for the image url, name, description and deliciousness
	2) Create a v-for loop that displays these food items onto the page, with all the data coming from the food array (hint: for the image src, use :src)
	3) Add your own food item to the list
	4) Create a child component and use it to display each of your items (don't use the components/Solution/Food.vue file)
	5) Add unique id's to the food array for each item, and apply these to a :key property on your v-for loop

	-->
  <q-page padding>
    <div class="q-pa-md row items-stretch">

      <card
        v-for="food in foods"
        :food="food"
        :key="food.id"
      >
      </card>

    </div>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      foods: [
        {
          name: 'Burger',
          id: 1,
          imageUrl: 'https://i.imgur.com/0umadnY.jpg',
          description: 'A burger is a sandwich consisting of one or more cooked patties of ground meat, usually beef, placed inside a sliced bread roll or bun.',
          deliciousness: 4
        },
        {
          name: 'Pizza',
          id: 2,
          imageUrl: 'https://i.imgur.com/b9zDbyb.jpg',
          description: 'Pizza is a savory dish of Italian origin, consisting of a usually round, flattened base of leavened wheat-based dough.',
          deliciousness: 5
        },
        {
          name: 'Sprouts',
          id: 3,
          imageUrl: 'https://i.imgur.com/RbKjUjB.jpg',
          description: 'The Brussels sprout is a member of the Gemmifera Group of cabbages, grown for its edible buds.',
          deliciousness: 1
        },
        {
          name: 'Sushi',
          id: 4,
          imageUrl: 'https://i.imgur.com/oWWatcX.jpg',
          description: 'Sushi is a popular Japanese dish made from seasoned rice with fish, egg, or vegetables. A sushi roll is shaped inside a thin sheet of seaweed.',
          deliciousness: 5
        }
      ]
    }
  },
  components: {
    card: require("../components/Card").default
  }
}
</script>

<style>
.card {
  flex-basis: 210px;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 5px;
  margin-right: 10px;
  margin-bottom: 10px;
}
.card img {
  max-width: 100%;
}
.card-content {
  padding: 0 10px;
}
h1 {
  font-size: 23px;
}
p {
  font-size: 14px;
}
</style>
