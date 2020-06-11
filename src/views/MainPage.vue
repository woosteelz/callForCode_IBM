<template>
  <v-container fill-height>
    <v-col cols="9">
      <div class="page-body">
        <!-- STORY 영역 -->
        <div class="story pb-1">
          <Story :allUsers="allUsers"></Story>
        </div>
        <!-- STORY 영역 끝 -->

        <!-- TOPIC 영역 -->
        <div class="topic pb-1">
          <Topic />
        </div>
        <!-- TOPIC 영역 끝-->

        <!-- FEED 영역 -->
        <div class="feed my-3">
          <Feed v-for="feed in feeds" :key="feeds.indexOf(feed)" :feed="feed" />
        </div>
        <!-- FEED 영역 끝 -->
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
                <v-btn text color="grey darken-1" @click="dialog = false"
                  >Cancel</v-btn
                >
                <v-spacer></v-spacer>
                <v-btn text color="primary" @click="dialog = false"
                  >Submit</v-btn
                >
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-app-bar>
      </div>
    </v-col>
  </v-container>
</template>

<script>
import Feed from "@/components/Feed.vue";
import Story from "@/components/Story.vue";
import Topic from "@/components/Topic.vue";
import feeds from "@/data/feeds.js";

export default {
  components: {
    Feed,
    Story,
    Topic,
  },
  data() {
    return {
      dialog: false,
      feeds,
      allUsers: [
        {
          id: 1,
        },
        {
          id: 2,
        },
        {
          id: 3,
        },
        {
          id: 4,
        },
        {
          id: 5,
        },
        {
          id: 6,
        },
        {
          id: 5,
        },
        {
          id: 5,
        },
        {
          id: 5,
        },
        {
          id: 5,
        },
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
          filter: "perpetua",
        },
      ],
      topics: [
        {
          id: 1,
          topic: "COVID - 19",
        },
        {
          id: 2,
          topic: "COVID - 19",
        },
        {
          id: 3,
          topic: "COVID - 19",
        },
        {
          id: 4,
          topic: "COVID - 19",
        },
      ],
    };
  },
  methods: {
    link() {},
  },
};
</script>

<style>
.rounded-card {
  border-radius: 50px;
}
</style>
