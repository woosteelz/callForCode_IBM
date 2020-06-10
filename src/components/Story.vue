<template>
  <v-card max-width="600" class="mx-auto my-3" tile outlined>
    <v-slide-group class="mx-auto" multiple show-arrows>
      <v-slide-item class="ma-3" v-for="user in allUsers" :key="allUsers.indexOf(user)">
        <v-avatar color="orange" size="62" @click="link">
          <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/1211695/me_3.jpg" />
        </v-avatar>
      </v-slide-item>
    </v-slide-group>
  </v-card>
</template>

<script>
export default {
  props: {
    allUsers: Array
  }
};
</script>

<style>
</style>>