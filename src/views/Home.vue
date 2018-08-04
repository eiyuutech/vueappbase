<template>
  <div class="home">
    <!-- <img src="../assets/logo.png"> -->
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <spinner v-if="loading"
      :status="loading"
      color="#ccc"></spinner>
    <p v-if="!loading">
      This text will show when loading is false
      <button @click="loadContent">Click to load</button></p>

  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Spinner from 'vue-spinner-component/src/Spinner.vue'

export default {
  name: 'home',
  data () {
    return {
      loading: false
    };
  },
  methods: {
    loadContent() {
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
      }, 3000);
    }
  },
  components: {
    HelloWorld,
    Spinner
  }
}
</script>
