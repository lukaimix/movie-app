<template>
  <div class="sidebar">
    <div class="sidebar-top">
      <h2><font-awesome-icon class="title" icon="clapperboard" />E-Movie</h2>
    </div>
    <nav class="nav">
      <div class="nav-menu">
        <h3>Menu</h3>
        <router-link to="/"><font-awesome-icon class="icon" icon="house-user" /> Home</router-link> 
        <router-link to="/movielistview"><font-awesome-icon class="icon" icon="rectangle-list" /> List</router-link>
        <router-link to="/friendsview"><font-awesome-icon class="icon" icon="user-group" /> Friends</router-link>
        <router-link to="/about"><font-awesome-icon class="icon" icon="heart" /> Favorite</router-link>
      </div>
      <div class="nav-payment">
        <h3>Payment</h3>      
        <router-link to="/cartview"><font-awesome-icon class="icon" icon="cart-shopping" /> Cart</router-link>
        <router-link to="/wishlistview"><font-awesome-icon class="icon" icon="heart-circle-check" /> Wish list</router-link>
      </div>
      <div class="nav-general">
        <h3>General</h3>      
        <router-link to="/settingsview"><font-awesome-icon class="icon" icon="gear" /> Settings</router-link>
        <a href="#"><font-awesome-icon class="icon" icon="right-from-bracket" />Logout</a>
      </div> 
    </nav>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  data() {
    return {
      film: {},
    };
  },
  components: {},
  watch: {},
  methods: {},
})
export default class HomeView extends Vue {}
</script>

<style lang="scss" scoped>

* {
  font-size: "Fira-sans";
}

.sidebar {
  min-width:200px;
  background-color: #121418;
  height: 100vh;
  .sidebar-top {
     margin: 1rem;
    .title {
      color: #00c39a;
    }
    h2 {
      color: #fff;
    }
  }

  nav {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    .nav-general, .nav-menu, .nav-payment {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      margin-left: 1rem;
    }
 
    .icon {
      color: #00c39a;
    }
    h3 {
      color: #fff;
    }

    a {
      margin-left: 0.3rem;
      text-decoration: none;
      color: #fff;
        &.router-link-exact-active {
          color: #42b983;
          border-right: solid 5px #42b983;
         }
    }
  }
}

</style>
