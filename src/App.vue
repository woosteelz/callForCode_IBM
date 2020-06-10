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
      <v-btn
        @click="dialog = !dialog"
        fab
        dark
        color="success"
        absolute
        top
        right
      >
        <v-icon x-large>mdi-plus</v-icon>
      </v-btn>
      <v-dialog v-model="dialog" max-width="500px">
        <v-card>
          <v-card-title>
            <strong>피드 작성</strong>
          </v-card-title>
          <v-divider />
          <v-card-text>
            <div class="pa-3" outlined>
              <v-file-input
                chips
                multiple
                :rules="rules"
                accept="image/png, image/jpeg, image/bmp"
                placeholder="Pick an image"
                prepend-icon="mdi-camera"
                counter
                show-size
              ></v-file-input>
            </div>
            <div class="pa-3">
              <v-textarea
                outlined
                name="input-7-4"
                placeholder="내용 입력..."
              ></v-textarea>
            </div>
          </v-card-text>
          <v-divider />
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
      dialog: false,
    };
  },
};
</script>
<style scoped>
#app {
  background-color: #fafafa;
}
</style>
