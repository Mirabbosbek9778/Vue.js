<template>
  <ul class="movie-list list-group">
    <MovieListItem v-for="movie in movies" :movie="movie" />
  </ul>
</template>

<script>
import MovieListItem from "../movie-list-item/MovieListItem.vue";
export default {
  components: { MovieListItem },
  data() {
    return {
      movies: [
        { name: "Ertugrul", viewers: 811, favourite: false, like: true },
        { name: "Kurtlar Vadisi", viewers: 830, favourite: false, like: true },
        { name: "KAra sevda", viewers: 785, favourite: false, like: true },
      ],
    };
  },
};
</script>

<style scoped>
.movie-list {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: white;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
