<template>
  <v-container fill-height>
    <v-col cols="9">
      <!-- STORY 영역 -->
      <div class="story">
        <Story :allUsers="allUsers"></Story>
      </div>
      <!-- STORY 영역 끝 -->

      <!-- TOPIC 영역 -->
      <v-sheet color="#fafafa" class="mx-auto" max-width="700">
        <v-slide-group class="px-10" multiple show-arrows>
          <v-slide-item v-for="n in 25" :key="n" v-slot:default="{ active, toggle }">
            <v-btn
              class="mx-2"
              height="100"
              :input-value="active"
              active-class="purple white--text"
              depressed
              rounded
              @click="toggle"
            >Options {{ n }}</v-btn>
          </v-slide-item>
        </v-slide-group>
      </v-sheet>
      <!-- TOPIC 영역 끝-->

      <!-- FEED 영역 -->
      <div class="feed">
        <Feed v-for="feed in feeds" :key="feeds.indexOf(feed)" :feed="feed" />
      </div>
      <!-- FEED 영역 끝 -->
    </v-col>

    <v-row justify="end">
      <v-btn @click="dialog = !dialog" depressed icon large dark color="success">
        <v-icon x-large>mdi-plus-circle-outline</v-icon>
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
    </v-row>
  </v-container>
</template>

<script>
import Feed from "@/components/Feed.vue";
import Story from "@/components/Story.vue";
import feeds from "@/data/feeds.js";

export default {
  components: {
    Feed,
    Story
  },
  data() {
    return {
      feeds,
      allUsers: [
        {
          id: 1
        },
        {
          id: 2
        },
        {
          id: 3
        },
        {
          id: 4
        },
        {
          id: 5
        },
        {
          id: 6
        },
        {
          id: 5
        },
        {
          id: 5
        },
        {
          id: 5
        },
        {
          id: 5
        }
      ],
      feedData: [
        {
          id: 1,
          username: "socleansofreshh",
          userImage:
            "https://s3-us-west-2.amazonaws.com/s.cdpn.io/1211695/me_3.jpg",
          postImage:
            "https://s3-us-west-2.amazonaws.com/s.cdpn.io/1211695/tropical_beach.jpg",
          likes: 36,
          hasBeenLiked: false,
          caption: "When you're ready for summer '18 ☀️",
          filter: "perpetua"
        }
      ],
      topics: [
        {
          id: 1,
          topic: "COVID - 19"
        },
        {
          id: 2,
          topic: "COVID - 19"
        },
        {
          id: 3,
          topic: "COVID - 19"
        },
        {
          id: 4,
          topic: "COVID - 19"
        }
      ]
    };
  },
  methods: {
    link() {}
  }
};
</script>

<style>
.rounded-card {
  border-radius: 50px;
}
</style>
