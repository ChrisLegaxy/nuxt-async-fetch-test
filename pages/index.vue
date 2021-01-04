<template>
  <div>
<!-- 
    <div v-if="$fetchState.pending">
      Loadingg
    </div>

    <div v-if="$fetchState.error">
      <v-btn @click="refreshPage">
        Refresh
      </v-btn>
    </div> -->

    <div>
      {{ res.userId }}
    </div>

    <nuxt-link to="/yeah" no-prefetch>
      Yeah
    </nuxt-link>

    <v-btn to="/about" nuxt>
      the about
    </v-btn>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  // activated() {
  //   // Call fetch again if last fetch more than a minute ago
  //   if (this.$fetchState.timestamp <= Date.now() - 30000) {
  //     this.$fetch()
  //   }
  // },
  // async fetch() {
  //   const res = await this.$axios.$get('https://jsonplaceholder.typicode.com/todos/1')

  //   console.log(res);
  // },
  async asyncData({$axios}) {
    const res = await $axios.$get('https://jsonplaceholder.typicode.com/todos/1')

    console.log(res);

    return {
      res
    }
  },
  // fetchOnServer: true,
  methods: {
    async refreshPage() {
      await this.$fetch()
    }
  }
});
</script>

<style scoped>
</style>