<template>
  <div class="favorites">
    <div class="favorites-header">
      <h1>Your Favorites</h1>
    </div>

    <FavoritesList/>
  </div>
</template>

<script>
// @ is an alias to /src
import FavoritesList from '@/components/FavoritesList.vue'

export default {
  name: 'Favorites',
  components: {
    FavoritesList
  }
}
</script>

<style scoped>
.favorites-header {
  display:flex;
  justify-content: center;
  align-items: center;
  margin-top:30px;
  margin-left:30px;
  margin-right:30px;
  margin-bottom:0;
}
</style>
