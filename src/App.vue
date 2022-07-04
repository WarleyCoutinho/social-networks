<script setup>
import Item from './components/Item.vue';
import Footer from './components/Footer.vue';
</script>

<script>
import Dados from './Dados/Services.json';

export default {
  data() {
    return {
      servicos: null,
    };
  },
  mounted() {
    // let target =
    //   'https://raw.githubusercontent.com/yurimarcon/link-services/main/src/Dados/Services.json';

    // fetch(target)
    //   .then((res) => res.json())
    //   .then((res) => (this.servicos = res))
    //   .catch((e) => console.log(e));
    this.servicos = Dados;
  },
};
</script>

<template>
  <img
    alt="Profile"
    style="width: 150px; border-radius: 50%"
    src="https://media-exp2.licdn.com/dms/image/C4D03AQFjK-3jk56Acw/profile-displayphoto-shrink_800_800/0/1631826529192?e=1662595200&v=beta&t=yWHpm0wzDlHmPiPWDxXJ8qwbQs-7i2ROlVigj-XKTEY"
  />
  <!-- <img
    alt="Profile"
    style="width: 150px; border-radius: 50%"
    src="./assets/warley.png"
  /> -->
  <h1>Warley Coutinho</h1>

  <blockquote cite="Engenharia de Software">
    <p>" JavaScript | Node.Js | Vue.Js |Vite.Js"</p>
    <h3><small> Dev Full Stack. </small></h3>
  </blockquote>

  <hr />
  <div class="items">
    <Item v-for="(servico, index) in servicos" :key="index" :item="servico" />
  </div>

  <Footer />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
  margin-bottom: 100px;
  min-height: calc(100vh - 120px);
}
html {
  /* background: url('./assets/VitexVuejsc.png'); */
  background: url('https://camo.githubusercontent.com/71982184b993bd0aa67c91afa29c03e9bc5a6b942ffa84473ce417534afbe358/68747470733a2f2f692e6962622e636f2f64346853636a762f62616e6e65722e706e67');
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100%;
}
.items {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
h1 {
  color: hsl(0, 8%, 5%);
}
h3 {
  font-weight: 900;
  color: hsl(0, 8%, 5%);
}
p {
  color: hsl(0, 8%, 5%);
  font-size: 18px;
}
</style>
