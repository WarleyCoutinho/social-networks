<template>
  <div class="card">
    <a :href="item.href">
      <img :src="item.img" alt="Icon " />
    </a>
    <span>{{ item.titulo }}</span>
  </div>
</template>

<script>
export default {
  props: ['item'],
};
</script>

<style scoped>
div {
  margin: 20px 50px 20px 50px;
  display: block;
  width: 100px;
}
img {
  width: 80px;
}
span {
  font-weight: 900;
}
.card {
  background-color: rgba(255, 255, 255, 0.5);
  display: flex;
  justify-content: center;
  flex-direction: column;
  min-width: 120px;
  min-height: 150px;
  border: 1px solid hsl(153, 90%, 52%);
  border-radius: 5%;
  opacity: 0.9;
  box-shadow: 0 0 2em rgb(243, 9, 9);
  transition: box-shadow 0.5s;
}
.card:hover {
  opacity: 1;
  box-shadow: 0 0 4em rgb(148, 238, 3);
}
@media (max-width: 600px) {
  div {
    margin: 20px 20px 20px 20px;
  }
}
</style>
