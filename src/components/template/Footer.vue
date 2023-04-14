<template>
  <footer>
    <span><strong class="strong"> Warley Coutinho</strong> </span
    ><span class="ano"
      >&copy; <strong class="strong">{{ currentYear }}</strong> Direitos
      Reservados.</span
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

<style scoped>
footer {
  width: 100%;
  /*border-top: 1px solid hsl(0, 0%, 81%);*/
  margin-left: -12px;
  background: rgba(0, 0, 0, 0.3);
  height: 30px;
  padding-top: 20px;
  position: fixed;
  bottom: 0;
  font-weight: 900;
}

.strong {
  color: hsl(0, 0%, 100%);
  padding-right: 10px;
  font-size: 18px;
  font-weight: 900;
}
.ano {
  color: rgb(243, 9, 9);
  font-size: 16px;
  padding-right: 10px;
}
</style>
