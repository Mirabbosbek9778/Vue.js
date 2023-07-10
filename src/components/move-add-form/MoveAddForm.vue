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
      if(!this.name || !this.viewers) return
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

<template>
  <div class="movie-add-form" @submit.prevent>
    <h3>Add New Movie</h3>
    <form class="add-form d-flex">
      <input
        type="text"
        class="name"
        placeholder="Qanday Kinolar?"
        :value="name"
        @input="name = $event.target.value"
      />
      <input
        type="number"
        class="number"
        placeholder="Nechchi marotaba korilgan?"
        :value="viewers"
        @input="viewers = $event.target.value"
      />
      <button class="add" type="submit" @click="addMovie">
        AddMovies
      </button>
    </form>
  </div>
</template>

<style>
.add-form{
  gap: 10px;
}
h3{
  cursor: pointer;
}
.name{
  width: 45%;
  border-radius: 10px;
  border: 0.3px solid black;
  padding-left:10px;
}
.number{
  padding-left:10px;
  cursor: pointer;
  width: 45%;
  border-radius: 10px;
  border: 0.3px solid black;
}
.add{
  background-color: yellow;
  border-radius: 20px;
  border: 1px solid black;
  color: rgb(73, 73, 207);
}
.movie-add-form {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: rgb(255, 255, 255);
  border-radius: 5px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
