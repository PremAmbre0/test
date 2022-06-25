<template>
  <div id=" app">
    <date-picker></date-picker>
  </div>
</template>

<script>
import DatePicker from './components/DatePicker.vue';
export default {
  name: "App",
  components: {
    DatePicker
  },
  data: () => ({
    //
  }),
  beforeMount() {
    const app = document.createElement('div');
    app.setAttribute('data-app', true);
    document.body.append(app);
  },
};
</script>
 <style lang="scss" scoped>
 #app {
   height: 76.8rem;
   width: 144.1rem;
 }
 </style>