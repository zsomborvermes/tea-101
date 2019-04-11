<template>
  <div id="detail">
    <h1>Tea-101</h1>
    <div class="main">
      <div class="left">
        <button
          type="button"
          v-bind:key="button.id"
          v-for="button in buttonList"
          v-on:click="handleClick(button.id)"
          v-bind:class="{activebtn:button.id===clickedButton}"
        >{{ button.name }}</button>
      </div>
      <div class="right">
        <div class="descriptions">
          <div>{{ buttonList[clickedButton - 1].text }}</div>
        </div>
      </div>
    </div>
    <div class="opinion" v-if="opinions.length > 0">
      <div class="image">
        <img
          src="http://factsanddetails.com/media/2/20111107-Wiki%20C%20%20TV%20Keye_Luke_Master_Po_Kung_Fu.JPG"
        >
        <p id="label">Antikrisztus {{ this.opinions[this.opinions.length - 1].name }}</p>
      </div>
      <div class="opinion-text">
        <p>"{{ this.opinions[this.opinions.length - 1].text }}"</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailPage",
  data() {
    return {
      buttonList: [
        { id: 1, name: "What is tea?", text: "Tea" },
        { id: 2, name: "What is White tea?", text: "White tea" },
        { id: 3, name: "What is Green tea?", text: "Green tea" },
        { id: 4, name: "What is Pu-erh tea?", text: "Pu-erh tea" },
        { id: 5, name: "What is Oolong tea?", text: "Oolong tea" },
        { id: 6, name: "What is Black tea?", text: "Black tea" }
      ],
      clickedButton: 1
    };
  },
  props: ["opinions"],
  methods: {
    handleClick(id) {
      this.clickedButton = id;
    }
  }
};
</script>

<style scoped>
#detail {
  height: 100vh;
  padding: 30px 100px;
  background-image: url("https://www.healthline.com/hlcmsresource/images/chamomile-tea.jpg");
  background-size: cover;
}

#label {
  font-size: 20px;
  font-weight: bold;
}

button {
  background-color: #eec642;
  border: 2px solid black;
  border-radius: 5px;
  font-size: 30px;
  font-weight: bold;
  padding: 12px 5px;
  margin-bottom: 15px;
}

h1 {
  font-size: 70px;
  color: black;
  margin: 0;
  margin-bottom: 50px;
  text-align: left;
}

img {
  height: 250px;
  width: 200px;
  border-radius: 200px;
  border: 3px solid black;
  align-self: center;
}

.main {
  display: flex;
  height: 50%;
}

.opinion {
  display: flex;
  height: 35%;
}

.image {
  display: flex;
  flex-direction: column;
  width: 30%;
}

.opinion-text {
  width: 65%;
  font-size: 30px;
  text-align: left;
  padding: 20px;
  border: 3px solid black;
  border-radius: 30px;
  background-color: white;
  height: 70%;
  text-justify: auto;
  margin-left: 50px;
}

.left {
  display: flex;
  flex-direction: column;
  width: 30%;
}

.right {
  display: flex;
  flex-direction: column;
  width: 70%;
  font-size: 100px;
  font-weight: bold;
}
.activebtn {
  background-color: blue;
  color: white;
}

.descriptions {
  height: 100%;
}
</style>


