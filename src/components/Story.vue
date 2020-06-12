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
            <v-avatar class="avatar" size="48" @click="link">
              <v-img :src="user.src" />
            </v-avatar>
          </v-btn>
        </div>
      </v-slide-item>
    </v-slide-group>
  </v-card>
</template>

<script>
export default {
  props: {
    allUsers: Array,
  },
  methods: {
    link() {},
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
