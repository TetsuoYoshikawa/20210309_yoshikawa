<template>
  <vue-ster animate="animated rubberBand" color="#F05654">
    <a slot="icon" class="fa fa-heart" @click="handleClick"></a>
  </vue-ster>
</template>

<script>
export default{
  mounted:{
    handleClick(){
      this.$refs.ThumsUp.$data.active = true;
      console.log(this.$refs.ThumsUp.$data);
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.ThumbsUp.$data);
    }
  }
}
</script>
