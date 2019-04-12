<template>
  <div id="app">
    <LandingPage/>
    <DetailPage v-bind:opinions="opinions"/>
    <OpinionPage v-on:form-submit="saveOpinion"/>
  </div>
</template>

<script>
import LandingPage from "./components/LandingPage.vue";
import DetailPage from "./components/DetailPage.vue";
import OpinionPage from "./components/OpinionPage.vue";

export default {
  name: "app",
  components: {
    LandingPage,
    DetailPage,
    OpinionPage
  },
  data() {
    return {
      opinions: []
    }
  },
  methods: {
    saveOpinion(formData) {
      this.opinions.push(formData);
    }
  }
};
</script>

<style>
html {
  scroll-behavior: smooth;
  padding: 0;
  margin: 0;
}

body {
  padding: 0;
  margin: 0;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
