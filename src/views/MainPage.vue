<template>
  <v-container fill-height>
    <v-col cols="9">
      <!-- STORY 영역 -->
      <v-card color="#fafafa" class="mx-auto" max-width="700" outlined tile>
        <v-slide-group class="px-10" show-arrows>
          <v-slide-item
            v-for="user in allUsers"
            :key="user.id"
            v-slot:default="{ active, toggle }"
          >
            <v-card
              height="100"
              width="100"
              @click="toggle"
              elevation="0"
              color="#fafafa"
              small
            >
              <v-layout align-center fill-height justify-center>
                <v-scale-transition>
                  <v-list-item-avatar color="grey" height="80" width="80">
                    <v-img
                      :src="
                        'http://mblogthumb2.phinf.naver.net/20150427_261/ninevincent_1430122791768m7oO1_JPEG/kakao_1.jpg?type=w2'
                      "
                    >
                    </v-img>
                  </v-list-item-avatar>
                </v-scale-transition>
              </v-layout>
            </v-card>
          </v-slide-item>
        </v-slide-group>
      </v-card>
      <!-- STORY 영역 끝 -->

      <!-- TOPIC 영역 -->
      <v-sheet color="#fafafa" class="mx-auto" max-width="700">
        <v-slide-group class="px-10" multiple show-arrows>
          <v-slide-item
            v-for="n in 25"
            :key="n"
            v-slot:default="{ active, toggle }"
          >
            <v-btn
              class="mx-2"
              height="100"
              :input-value="active"
              active-class="purple white--text"
              depressed
              rounded
              @click="toggle"
            >
              Options {{ n }}
            </v-btn>
          </v-slide-item>
        </v-slide-group>
      </v-sheet>
      <!-- TOPIC 영역 끝-->

      <!-- FEED 영역 -->
      <v-card flat color="#fafafa">
        <Feed v-for="feed in feeds" :key="feeds.indexOf(feed)" :feed="feed" />
      </v-card>
      <!-- FEED 영역 끝 -->
    </v-col>

    <v-row justify="end">
      <v-btn
        @click="dialog = !dialog"
        depressed
        icon
        large
        dark
        color="success"
      >
        <v-icon x-large>mdi-plus-circle-outline</v-icon>
      </v-btn>
      <v-dialog v-model="dialog" max-width="500px">
        <v-card>
          <addSite />
        </v-card>
      </v-dialog>
    </v-row>
  </v-container>
</template>

<script>
import Feed from "@/components/Feed.vue";
import feeds from "@/data/feeds.js";

export default {
  components: {
    Feed,
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
};
</script>

<style>
.rounded-card {
  border-radius: 50px;
}
</style>
