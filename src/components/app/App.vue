<script>

import AppInfo from "../app-info/AppInfo.vue";
import SearchPanel from "../SearchPanel.vue";
import AppFilter from "../app-filter/AppFilter.vue";
import MoveList from "../move-list/MoveList.vue";
import MoveAddForm from "../move-add-form/MoveAddForm.vue";
import axios from 'axios'
        
export default {
   components: {
   AppInfo,
   SearchPanel,
   AppFilter,
   MoveList,
   MoveAddForm,
},
  data() {
    return {
        movies: [],
          term:''
         };
        
       },
     methods: {
       createMovie(item) {

          this.movies.push(item);
               },
            onToggleHandler({id,prop}) {
              this.movies=this.movies.map((item) => {
                if (item.id == id) {
                  return {...item , [prop] : ! item [prop]}
                }
                return item;
              });
            },
            onDeleteHandler(id){
              this.movies=this.movies.filter(c=>c.id != id)
            },
            onSearchHandler(arr,term){
               if(term.length==0){
                return arr
               }

               return arr.filter(c=>c.name.toLowerCase().indexOf(term)>-1)
            },
            updateTerm(term){
              this.term=term
            },
            async fetchMovie(){
              try {
                const {data}=await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
                const newArr=data.map(item=>({
                  id:item.id,
                  name:item.title,
                  like:false,
                  favourite:false,
                  viewers:item.id*10,
                }))
                this.movies=newArr
              } catch (error) {
                alert(error.message);
              }
            }
          },
          mounted() {
            this.fetchMovie()
          },
        }
</script> 

<template>
  <div class="app font-monospace">
    <div class="content">
      <AppInfo
        :allMoviesCount="movies.length"
        :favouriteMoviesCount="movies.filter((c)=>c.favourite).length"
      />
      <div class="search-panel">
        <SearchPanel :updateTerm="updateTerm"/>
        <AppFilter />
      </div>
      <MoveList :movies="onSearchHandler(movies,term)" @onToggle="onToggleHandler"  @onDelete="onDeleteHandler"/>
      <MoveAddForm @createMovie="createMovie" />
    </div>
  </div>
</template>

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




// const getFiltr = ({ key, value }) => {
//   let res = students.filter((user) =>
//     `${user[key]}`.toLowerCase().includes(`${value}`.toLowerCase())
//   );
//   students = res;
// };