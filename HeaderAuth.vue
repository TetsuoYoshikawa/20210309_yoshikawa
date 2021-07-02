<template>
  <div class="right flex">
    <select class="search" v-model="searchPrefecture">
      <option value="">All Prefecutes</option>
      <option v-for="(Prefecute,index) in prefecutureList" :key="index" :value="prefecute.id">{{prefecute.name}}</option>
    </select>
    <select class="search" v-model="searchGenre">
      <option value="">All Genre</option>
      <option v-for="(genre,index) in genreList" :key="index" :value="genre.id">{{genre.name}}</option>
    </select>
    <input type="text" placeholder="Restaurant Name" v-model="searchRestaurant">
    <button class="button" type="submit" @click="searching">Search</button>
  </div>
</template>

<script>
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
  computed:{
    prefectureList(){
    　return this.searchPrefecture.filter(searchPrefecture => {
        return searchPrefecture.name.includes(this.searchPrefecture)
    　})
    }
  },
};
</script>
