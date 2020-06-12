<template>
  <v-container>
    <v-col cols="12">
      <div class="page-body">
        <div class="story pb-1">
          <div class="pa-3">
            <h1>Weekly 6 Topic</h1>
            <v-spacer />
            <h2 class="blue--text">Science</h2>
          </div>

          <div class="pa-3">
            <h2>{{ articles[0].title }}</h2>
          </div>

          <div class="px-3 pt-1">
            <h4 class="grey--text">
              {{ articles[0].description }}
            </h4>
          </div>

          <div class="pa-3">
            {{ articles[0].content }}
            <div class="blue--text" @click="$router.push(articles[0].url)">
              ...view more
            </div>
          </div>

          <div class="mt-1">
            <v-divider class="mb-1 py-2"></v-divider>
            <v-card-text
              v-for="comment in articelComments"
              :key="articelComments.indexOf(comment)"
              class="py-0 mb-2 font-weight-bold"
              v-text="`${comment.username} ${comment.comment}`"
            ></v-card-text>
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
              </template>
            </v-textarea>
          </div>
        </div>
      </div>
    </v-col>
  </v-container>
</template>

<script>
import articles from "@/data/articles.js";
import articelComments from "@/data/articelComments.js";

export default {
  data() {
    return {
      articles,
      articelComments,
    };
  },
};
</script>
