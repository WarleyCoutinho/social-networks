<script setup>
import Content from './components/template/Content.vue';
import Footer from './components/template/Footer.vue';
</script>

<script>
// import Dados from './Dados/Services.json';

export default {
  comments: { Content, Footer },
  data() {
    return {
      servicos: null,
    };
  },
  mounted() {
    let target =
      'https://raw.githubusercontent.com/WarleyCoutinho/social-networks/main/src/Dados/Services.json';

    fetch(target)
      .then((res) => res.json())
      .then((res) => (this.servicos = res))
      .catch((e) => console.log(e));

    // this.servicos = Dados;
  },
};
</script>

<template>
  <img
    alt="Profile"
    style="width: 150px; border-radius: 50%"
    src="https://media-exp2.licdn.com/dms/image/C4D03AQHkbSg7bZHHMA/profile-displayphoto-shrink_800_800/0/1657027971428?e=1662595200&v=beta&t=bF5Yroqxvdw6U22a8acvqOh7IFGjOIfA69HqjIoa8x4"
  />
  <h1>Warley Coutinho</h1>

  <blockquote cite="Engenharia de Software">
    <p>JavaScript | Node.Js | Vue.Js | Vite.Js</p>
    <h3><small> Dev Full Stack Engineer. </small></h3>
  </blockquote>

  <hr />
  <div class="items">
    <Content
      v-for="(servico, index) in servicos"
      :key="index"
      :item="servico"
    />
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
  background: url('https://vuejsdevelopers.com/images/posts/versions/vite_vue_cli_1200.jpg');
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
  color: hsl(0, 0%, 100%);
}
h3 {
  font-weight: 900;
  color: hsl(83, 93%, 49%);
}
p {
  color: hsl(0, 0%, 100%);
  font-size: 18px;
}
</style>
