<template>
  <div class="landing">
    <div class="content">
      <h1>Delicious</h1>
      <h1>Delighs</h1>
      <a href="#detail">Check'em out!</a>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.landing {
  height: 100vh;
  background-image: url("https://cms.splendidtable.org/sites/default/files/styles/w2000/public/cedar-tea_by_Mette-Nielsen-LEDE.jpg?itok=P-UvOBBE");
  background-size: cover;
}
.content {
  position: absolute;
  right: 0px;
  width: 50%;
  padding: 10px;
}
a {
  text-decoration: none;
  color: black;
  background-color: #eec642;
  border: 3px solid black;
  border-radius: 5px;
  font-size: 50px;
  font-weight: bold;
  padding: 12px 5px;
}
h1 {
  font-size: 150px;
  color: black;
  margin: 0;
}
</style>


