<template>
  <v-card max-width="600" class="mx-auto my-3" tile outlined>
    <v-list-item class="px-4 py-1">
      <v-list-item-avatar
        class="my-0 mr-4"
        height="32px"
        width="32px"
        min-height="32px"
        min-width="32px"
        ><v-img :src="feed.userImage" height="32px" width="32px"
      /></v-list-item-avatar>
      <v-list-item-content class="pa-0">
        <v-list-item-title class="subtitle-2">{{
          feed.username
        }}</v-list-item-title>
      </v-list-item-content>
    </v-list-item>
    <v-divider />
    <v-img :src="feed.postImage" height="auto"></v-img>
    <v-card-text class="pb-1">
      {{ feed.caption }}
    </v-card-text>

    <v-card-actions class="py-0 mt-1">
      <v-btn icon>
        <v-icon>mdi-heart-outline</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-share-variant</v-icon>
      </v-btn>
    </v-card-actions>
    <v-card-text class="py-0 mb-2 font-weight-bold">
      좋아요 {{ feed.likes }}개
    </v-card-text>
    <v-card-text
      v-for="comment in feed.comments"
      :key="feed.comments.indexOf(comment)"
      class="py-0 mb-2 font-weight-bold"
    >
      {{ comment.username }} {{ comment.comment }}
    </v-card-text>
    <v-card-text class="py-0 mb-1 overline">
      1시간 전
    </v-card-text>
    <div class="mt-1">
      <v-divider class="mb-1"></v-divider>
      <v-textarea
        class="mb-1"
        name="input"
        rows="1"
        flat
        auto-grow
        dense
        solo
        placeholder="댓글 달기..."
        hide-details
        v-model="comment"
      >
        <template #append>
          <v-btn
            icon
            depressed
            small
            class="pb-1"
            @click="leaveComment({ username, userImage, comment })"
          >
            <v-icon>mdi-send</v-icon>
          </v-btn>
        </template></v-textarea
      >
    </div>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      username: "1111",
      userImage:
        "https://s3-us-west-2.amazonaws.com/s.cdpn.io/1211695/me_3.jpg",
      comment: "",
    };
  },
  props: {
    feed: Object,
  },
  methods: {
    leaveComment({ username, userImage, comment }) {
      this.feed.comments.push({ username, userImage, comment });
    },
  },
};
</script>

<style></style>
