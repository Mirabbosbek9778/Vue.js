<template>
  <div>
    <h1>Counter:{{ counter }}</h1>
    <div class="d-flex">
      <div @click="onIncreament" class="btn btn-success">ADD</div>
      <div @click="onDecrement" class="btn btn-danger">Delete</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    onIncreament() {
      this.counter += 1;
    },
    onDecrement() {
      this.counter -= 1;
    },
  },
};
</script>

<style></style>
 