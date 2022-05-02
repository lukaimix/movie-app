<template>
  <div class="app">
     <sidebar />
    <router-view class="view" />
  </div>
</template>
<script lang="ts">
import { Options, Vue } from "vue-class-component";
import sidebar from "./components/Sidebar.vue";
 
@Options({
  data() {
    return {
      film: {},
    };
  },
  components: { sidebar  },
  watch: {},
  methods: {},
  // mounted() {},
})
export default class HomeView extends Vue {}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

 
.app {
  background-color: #1b1f24;
  display: flex;
  overflow: hidden;
}
</style>
