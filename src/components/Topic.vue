<template>
  <v-card max-width="600" class="mx-auto my-3" tile outlined>
    <v-slide-group class="mx-auto" multiple show-arrows>
      <v-slide-item
        class="ma-2"
        v-for="n in topics"
        :key="topics.indexOf(n)"
        v-slot:default="{ active, toggle }"
      >
        <v-btn
          height="100"
          :input-value="active"
          active-class="purple white--text"
          depressed
          rounded
          @click="toggle"
          >{{ n.topic }}</v-btn
        >
      </v-slide-item>
    </v-slide-group>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      topics: [
        {
          id: 1,
          topic: "COVID - 19",
        },
        {
          id: 2,
          topic: "기후변화",
        },
        {
          id: 3,
          topic: "여행",
        },
        {
          id: 4,
          topic: "스포츠",
        },
      ],
    };
  },
};
</script>
