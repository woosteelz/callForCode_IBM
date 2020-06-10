<template>
  <v-app>
    <v-app-bar app max-height="48px" color="white" dense>
      <v-toolbar-title>
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
    <v-app-bar app max-height="48px" color="white" dense bottom>
      <v-btn @click="dialog = !dialog" fab dark color="success" absolute top right>
        <v-icon x-large>mdi-plus</v-icon>
      </v-btn>
      <v-dialog v-model="dialog" max-width="500px">
        <v-card>
          <v-card-text>
            <v-text-field label="File name"></v-text-field>

            <small class="grey--text">* This doesn't actually save.</small>
          </v-card-text>

          <v-card-actions>
            <v-spacer></v-spacer>

            <v-btn text color="primary" @click="dialog = false">Submit</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-app-bar>

    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>
<script>
export default {
  data() {
    return {
      dialog: false
    };
  }
};
</script>
<style scoped>
#app {
  background-color: #fafafa;
}
</style>
