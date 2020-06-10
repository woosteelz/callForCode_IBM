<template>
  <v-app>
    <v-app-bar app max-height="48px" color="white" dense>
      <v-tool-bar-title><strong>IBMproject</strong></v-tool-bar-title>

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
<style scoped>
#app {
  background-color: #fafafa;
}
</style>
