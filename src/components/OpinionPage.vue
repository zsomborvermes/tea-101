<template>
  <div class="opinion">
    <OpinionForm v-on:form-submit="emitFormSubmit"/>
  </div>
</template>
<script>
import OpinionForm from "./OpinionForm.vue";

export default {
  name: "OpinionPage",
  components: {
    OpinionForm
  },
  methods: {
    emitFormSubmit(formData) {
      this.$emit("form-submit", formData);
    }
  }
};
</script>
<style scoped>
.opinion {
  height: 100vh;
  background-image: url("https://qualityteacoffee.com/services/tea.jpg");
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  flex-direction: column;
}
</style>

