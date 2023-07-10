<script>
export default {
  props:{
    updateTerm:{
      type:Function,
      required:true,
    }
  },
  data() {
    return {
     term:'', 
    }
  },
  methods:{
    changeHandler(e){
      this.term = e.target.value
      this.updateTerm(this.term)
    }
  }
};
</script>

<template>
  <input
    type="text"
    class="form-control search-input"
    placeholder="Kinolarni qidirish"
    :value="term"
    @input="changeHandler"    
  />
</template>


<style scoped>
.search-input { 
  font-family: cursive;
  margin-bottom: 1rem;
  padding: 1.5rem;
  background-color: rgb(194, 165, 165);
  border-radius: 20px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
