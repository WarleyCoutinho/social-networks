<script setup>
import Content from './components/template/Content.vue';
import Footer from './components/template/Footer.vue';
</script>

<script>
import Dados from './Dados/Services.json';
import moment from 'moment';

export default {
  comments: { Content, Footer },
  data() {
    return {
      hours: moment().format(' L HH:mm:ss'),
      servicos: null,
    };
  },

  mounted() {
    // let target =
    //   'https://raw.githubusercontent.com/WarleyCoutinho/social-networks/main/src/Dados/Services.json';

    // fetch(target)
    //   .then((res) => res.json())
    //   .then((res) => (this.servicos = res))
    //   .catch((e) => console.log(e));

    setInterval(() => {
      this.hours = moment().format(' L HH:mm:ss');
    }, 1000);

    this.servicos = Dados;
  },
};
</script>

<template>
  <img
    alt="Profile"
    style="width: 150px; border-radius: 50%"
    src="./assets/wc.jpg"
  />
  <h1>Warley Coutinho</h1>

  <blockquote cite="Engenharia de Software">
    <strong class="qualificacao"
      >JavaScript | Vue.Js |Node.Js | Vite.Js | Tailwind CSS</strong
    >
    <h3>
      <small><strong>Dev Full Stack Engineer.</strong></small>
    </h3>
  </blockquote>
  <section>
    <span class="clock"
      ><strong>Hoje:{{ hours }}</strong></span
    >
  </section>

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
  color: hsl(210, 29%, 24%);
  margin-top: 20px;
  margin-bottom: 100px;
  min-height: calc(100vh - 120px);
}

/*html {
  background: url('https://vuejsdevelopers.com/images/posts/versions/vite_vue_cli_1200.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100%;
}*/

body {
  background: radial-gradient(hsl(0, 0%, 0%) 15%, transparent 16%) 0 0,
    radial-gradient(hsl(0, 0%, 0%) 15%, transparent 16%) 8px 8px,
    radial-gradient(hsla(0, 0%, 100%, 0.1) 15%, transparent 20%) 0 1px,
    radial-gradient(hsla(0, 0%, 100%, 0.1) 15%, transparent 20%) 8px 9px;
  background-color: hsl(0, 0%, 16%);
  background-size: 16px 16px;
  overflow-x: hidden;
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
  color: hsl(0, 0%, 100%);
}
.qualificacao {
  color: hsl(0, 0%, 100%);
  font-size: 18px;
}
.clock {
  color: hsl(0, 0%, 100%);
  border-radius: 5px;
  justify-content: center;
  width: 60%;
}
</style>
