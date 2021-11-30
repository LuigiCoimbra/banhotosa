<template>
  <v-app>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',

  data() {
    return {
      info: null,
    };
  },
  mounted() {
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then((response) => { this.info = response; });
  },
};
</script>
