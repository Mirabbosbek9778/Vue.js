<template>
  <div class="movie-add-form" @submit.prevent>
    <h3>Yangi kino qoshish</h3>
    <form class="add-form d-flex">
      <input
        type="text"
        class="form-control new-movie-label"
        placeholder="Qanday Kinolar?"
        :value="name"
        @input="name = $event.target.value"
      />
      <input
        type="number"
        class="form-control new-movie-label"
        placeholder="Nechchi marotaba korilgan?"
        :value="viewers"
        @input="viewers = $event.target.value"
      />
      <button class="btn btn-outline-dark" type="submit" @click="addMovie">
        qoshish
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      viewers: "",
    };
  },
  methods: {
    addMovie() {
      const newMovie = {
        name: this.name,
        viewers: this.viewers,
        favourite: false,
        like: false,
        id:Date.now()
      };
      this.$emit("createMovie", newMovie);
      this.name = "";
      this.viewers = "";
    },
  },
};
</script>

<style>
.movie-add-form {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: rgb(255, 255, 255);
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
