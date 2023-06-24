<template>
  <div class="movie-add-form">
    <h3>Yangi kino qoshish</h3>
    <form class="add-form d-flex">
      <input
        type="text"
        class="form-control new-movie-label"
        placeholder="Qanday Kinolar?"
      />
      <input
        type="text"
        class="form-control new-movie-label"
        placeholder="Nechchi marotaba korilgan?"
      />
      <button class="btn btn-outline-dark" type="submit">qoshish</button>
    </form>
  </div>
</template>

<script>
export default {};
</script>

<style>
.movie-add-form {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: white;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
