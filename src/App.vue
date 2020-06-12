<template>
  <v-app>
    <v-app-bar app max-height="48px" color="white" dense>
      <v-toolbar-title @click="$router.push({ name: 'Home' })">
        <strong>IBMproject</strong>
      </v-toolbar-title>

      <v-spacer />

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>
<script>
export default {
  data() {
    return {};
  },
};
</script>
<style scoped>
#app {
  background-color: #fafafa;
}
</style>
