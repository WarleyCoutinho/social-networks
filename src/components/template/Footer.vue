<template>
  <footer>
    <span><strong class="strong"> Warley Coutinho</strong> </span
    ><span class="ano"
      >&copy; <strong class="strong">{{ currentYear }}</strong> Todos os
      Direitos Reservados.</span
    >
  </footer>
</template>

<script>
import moment from 'moment';

export default {
  computed: {
    currentYear(value) {
      return moment(value).format('YYYY');
    },
  },
};
</script>

<style>
footer {
  width: 100%;
  border-top: 1px solid rgb(207, 207, 207);
  height: 40px;
  padding-top: 20px;
  background-color: honeydew;
  position: fixed;
  bottom: 0;
  font-weight: 900;
}

strong {
  color: hsl(83, 93%, 49%);
  padding-right: 10px;
  font-size: 18px;
  font-weight: 900;
}
.ano {
  color: #314657;
  font-size: 16px;
  padding-right: 10px;
}
</style>
