<template>
  <div class="home">
    <div>
      <h1>Je suis dans la page Home</h1>
    </div>
     <div>
    <div class="home-body">
      <MovieList class="movie"   />
      <SidebarRight class="sidebar" />

    </div>
    </div> 
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import axios from "axios";
import MovieList from "../components/MovieList.vue"
import SidebarRight from "../components/SidebarRight.vue"
@Options({
  components: {MovieList, SidebarRight},
  data() {
    return {
      film: {},
      name: "",
      result: [],
    };
  },

  watch: {
    name() {
      this.searchMovie();
    },
  },
  methods: {
    async searchMovie() {
      let result = await axios.get(
        "https://api.themoviedb.org/3/search/movie?api_key=6dc646632d1c11debbc7e874ea32f797&language=en-US&query=" +
          this.name +
          "&page=1&include_adult=false"
      );
      this.result = result.data.results;
      console.log(this.result)
    },
    async castMovie() {
      let result = await axios.get("https://api.themoviedb.org/3/movie/672/credits?api_key=6dc646632d1c11debbc7e874ea32f797&language=en-US")
      console.log(result.data)
    }
    // async getPopularMovie() {
    //   let result = await axios.get(
    //     "https://api.themoviedb.org/3/movie/top_rated?api_key=6dc646632d1c11debbc7e874ea32f797&language=en-US&page=1"
    //   );
    // },
  },mounted() {
    this.castMovie()
  }
})
export default class HomeView extends Vue {}
</script>

<style lang="scss" scoped>
.home {
  display: flex;
  flex-direction: column;
  overflow-x: hidden;
  overflow-y: hidden;
  width: 100%;
  min-height: 100vh;

  .home-body {
    display: flex;
    width: 100%;
      .movie {
      max-width: 60%;
      overflow: hidden;
      margin: 0  0.2rem;
    }
    
  }
}
</style>
