<template>
  <form v-on:submit.prevent="handleSubmit">
    <h1>Leave your opinion</h1>
    <label for="name">Name</label>
    <input v-model="opinion.name" type="text" id="name" placeholder="Type here...">
    <label for="opinion">Opinion</label>
    <textarea v-model="opinion.text" id="opinion" rows="10" placeholder="Type here..."></textarea>
    <button>Submit</button>
  </form>
</template>
<script>
export default {
  name: "OpinionForm",
  data() {
    return {
      opinion: {
        name: "",
        text: ""
      }
    };
  },
  methods: {
    handleSubmit() {
      if (this.opinion.name && this.opinion.text) {
        this.$emit("form-submit", this.opinion);
        this.opinion = {
          name: "",
          text: ""
        };
      } else {
        alert("Please fill out every part of the form!");
      }
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  width: 30%;
}
label {
  font-size: 15px;
  font-weight: bold;
  text-transform: uppercase;
  align-self: flex-start;
}

input {
  padding: 5px;
  height: 30px;
  font-size: 15px;
  margin-bottom: 10px;
  border: 2px solid lightgray;
  border-radius: 10px;
}

textarea {
  padding: 10px;
  font-size: 15px;
  resize: vertical;
  border: 2px solid lightgray;
  border-radius: 10px;
}

h1 {
  font-size: 55px;
  font-weight: bold;
}

button {
  background-color: #eec642;
  border: 2px solid black;
  border-radius: 5px;
  font-size: 20px;
  font-weight: bold;
  padding: 6px 2px;
  margin-top: 15px;
  width: 20%;
  align-self: flex-end;
}
</style>


