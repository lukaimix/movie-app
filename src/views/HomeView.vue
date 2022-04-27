<template>
  <div class="home">
    <input type="text" v-model="name" />
    <ul>
      <li v-for="(movie, index) in result" :key="index">
        <img
          :src="
            'https://www.themoviedb.org/t/p/w220_and_h330_face/' +
            movie.backdrop_path
          "
          :alt="movie.original_title"
        />
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import axios from "axios";

@Options({
  data() {
    return {
      film: {},
      name: "",
      result: [],
    };
  },
  components: {},
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
      console.log(result);
      this.result = result.data.results;
      console.log(this.result);
    },
  },
  // mounted() {},
})
export default class HomeView extends Vue {}
</script>

<style lang="scss" scoped>
ul {
  display: flex;
  flex-wrap: wrap;
  li {
    list-style-type: none;
    img {
      width: 250px;
      height: 250px;
    }
  }
}
</style>
