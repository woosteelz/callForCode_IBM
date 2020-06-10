<template>
  <v-card max-width="600" class="mx-auto my-3" tile outlined>
    <v-slide-group class="mx-auto" multiple show-arrows>
      <v-slide-item
        class="ma-2"
        v-for="n in 25"
        :key="n"
        v-slot:default="{ active, toggle }"
      >
        <v-btn
          height="100"
          :input-value="active"
          active-class="purple white--text"
          depressed
          rounded
          @click="toggle"
          >Options {{ n }}</v-btn
        >
      </v-slide-item>
    </v-slide-group>
  </v-card>
</template>

<script>
export default {};
</script>
