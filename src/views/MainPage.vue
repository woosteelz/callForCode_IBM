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
