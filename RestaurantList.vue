<template>
  <div>
    <HeaderAuth />
    <RestaurantList />
  </div>
</template>

<script>
import HeaderAuth from '../components/HeaderAuth.vue';
import Favorite from '../components/Favorite.vue';
import RestaurantList from '../components/RestaurantList.vue';
export default{
  data(){
    return{
      searchPrefecture:"",
      searchGenre:"",
      searchRestaurant:"",
      prefectureList:[
        {name:"大阪"}
      ],
      genreList:[
        {name:"焼肉"}
      ],
      restaurantList:[
        {name:"root",prefecture:"大阪",genre:"焼肉"}
      ],
    };
  },
  components:{
    HeaderAuth,
    Favorite,
    RestaurantList
  }
};
</script>
