<template>
  <div class="movie-component">
   <!-- <div class="item">
     <font-awesome-icon class="icon" icon="magnifying-glass" />
     <input type="text" placeholder="Search" v-model="name">
   </div> -->
   <img id="poster" src="https://vmndims.binge.com.au/api/v2/img/5ffbe602e4b0a94dcf2aed96-1610343945498?location=tile&imwidth=1280" alt="">
    <div>
    <h3>Popular Actor</h3>
    <ul>
      <li v-for="(actor,index) in result" :key="index">
        {{ actor.name }}
        <img
        id="actor_img"
          :src='
            "https://www.themoviedb.org/t/p/w220_and_h330_face/" +
            actor.profile_path'
          :alt="actor.name">
      </li>
    </ul>
    </div>
    <p>Current Movie</p>
    <ul id="list">
      <li v-for="(actor,index) in potter" :key="index">
        {{ actor.name }}
        <img
        id="actor_img"
          :src='
            "https://www.themoviedb.org/t/p/w220_and_h330_face/" +
            actor.poster_path'
          :alt="actor.name">
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import axios from "axios";
import MovieList from "../components/MovieList.vue"
@Options({
  components: {MovieList},
  data() {
    return {
      result: [],
      potter:[]
    };
  },

  watch: {
  },

  methods: {
    async getPopularActor() {
      let result = await axios.get(
       "https://api.themoviedb.org/3/movie/672/credits?api_key=6dc646632d1c11debbc7e874ea32f797&language=en-US"
      );
      this.result = result.data.cast;
    },
    async getHarryPotterMovie() {
      let result = await axios.get(
        "https://api.themoviedb.org/3/search/movie?api_key=6dc646632d1c11debbc7e874ea32f797&language=en-US&query=harry potter&page=1&include_adult=false"
      );
      console.log(result.data)
      let tab = []
     tab = result.data.results;

      let i = 0
      for (const iterator of tab) {
        console.log(iterator)
        if(i <3) {
          this.potter.push(iterator)
        } else {
          break;
        }
        i++
      }
    }
  },
  mounted(){
   this.getPopularActor()
   this.getHarryPotterMovie()
  }
})
export default class HomeView extends Vue {}
</script>

<style lang="scss" scoped> 
.movie-component {
    overflow-y: hidden;
    overflow-x: hidden;
    height: 90vh;

 .item {
  background-color:  #121418;
  display: flex;
  padding: 0.5rem;

  .icon {
    color: #737375;
    padding : 0 0.2rem;
  }

  input {
    padding-left: 0.3rem;
    background: none;
    outline: none;
    border: none;
    color: #737375;
    width: 100%;
    &::placeholder {
      color: #737375;
    }
    &:focus {
      outline: none;
    }
  }
}

  #poster {  
      width: 75%;
      height: 220px;
      border-radius: 9px;
      margin: 0.5rem;
  }

  ul {
  display: flex; 
  width: 100%;
  margin-left: 2rem;
  
    li {
      list-style-type: none;
      color: #fff;
      margin: 0 1rem;
      img {
        width: 250px;
        height: 250px;
      }
      #actor_img {
        height: 100px;
        width: 120px;
      }
    }
  }

  #list {
    li {
      img {
      width: 202px;
      height: 200px;
    }
    }
  }
}
</style>