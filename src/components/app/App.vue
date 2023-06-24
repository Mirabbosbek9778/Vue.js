<template>
  <div class="app font-monospace">
    <div class="content">
      <AppInfo />
      <div class="search-panel">
        <SearchPanel />
        <AppFilter />
    </div>
        <MoveList />
        <MoveAddForm/>
    </div> 
  </div>
</template>

<script>
import AppInfo from "../app-info/AppInfo.vue";
import SearchPanel from "../SearchPanel.vue";
import AppFilter from "../app-filter/AppFilter.vue";
import MoveList from "../move-list/MoveList.vue";
import MoveAddForm from "../move-add-form/MoveAddForm.vue";

export default {
  components: {
    AppInfo,
    SearchPanel, 
    AppFilter,
    MoveList,
    MoveAddForm,
  },
};  
</script>

<style>
.app {
  height: 100vh;
  color: black;
}
.content {
  width: 1000px;
  min-height: 700px;
  background-color: bisque;
  margin: 0 auto;
  padding: 5rem 0;
}
.search-panel {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: rgb(255, 255, 255);
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);    
}
</style>
