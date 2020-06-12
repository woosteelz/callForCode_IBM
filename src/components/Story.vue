<template>
  <v-card max-width="600" class="mx-auto my-3" tile outlined>
    <v-slide-group class="mx-auto" multiple show-arrows>
      <v-slide-item
        class="ma-3"
        v-for="user in allUsers"
        :key="allUsers.indexOf(user)"
      >
        <div class="btn-wrapper">
          <v-btn class="button" fab icon>
            <v-avatar class="avatar" size="48" @click.stop="user.dialog = true">
              <v-img :src="user.src" />
            </v-avatar>
          </v-btn>
          <v-dialog v-model="user.dialog" max-width="290">
            <v-card>
              <v-card-title class="headline"
                >Daily Mission is Here!</v-card-title
              >

              <v-card-text>
                {{ user.detail }}
              </v-card-text>

              <v-card-actions>
                <v-btn color="green darken-1" text @click="user.dialog = false">
                  Close
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn color="green darken-1" text @click="user.dialog = false">
                  Agree
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </div>
      </v-slide-item>
    </v-slide-group>
  </v-card>
</template>

<script>
import allUsers from "@/data/allUsers.js";
export default {
  methods: {
    link() {},
  },
  data() {
    return {
      allUsers,
    };
  },
};
</script>

<style>
.btn-wrapper {
  background: linear-gradient(to right, red, orange);
  border-radius: 70%;
  animation: spin 1s linear infinite;
  padding: 2px;
}
.button {
  background: #fff;
  border-radius: 70%;
}
</style>
