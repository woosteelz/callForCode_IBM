<template>
  <v-container>
    <v-col cols="9">
      <div class="page-body">
        <!-- STORY 영역 -->
        <div class="story pb-1">
          <v-card max-width="600" class="mx-auto my-3" tile outlined>
            <v-slide-group class="mx-auto" multiple show-arrows>
              <v-slide-item class="ma-3" v-for="n in 6" :key="n">
                <div class="btn-wrapper">
                  <v-hover v-slot:default="{ hover }">
                    <v-btn
                      class="button"
                      v-if="hover"
                      icon
                      x-large
                      height="48"
                      width="48"
                    >
                      <v-icon x-large>
                        mdi-delete-forever
                      </v-icon>
                    </v-btn>
                    <v-btn v-else class="button" fab icon>
                      <v-avatar class="avatar" size="48" @click="link">
                        <v-img
                          src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/1211695/me_3.jpg"
                        >
                        </v-img>
                      </v-avatar>
                    </v-btn>
                  </v-hover>
                </div>
              </v-slide-item>
            </v-slide-group>
          </v-card>
        </div>
        <!-- STORY 영역 끝 -->

        <!-- TOPIC 영역 -->
        <div class="topic pb-1">
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
        </div>
        <!-- TOPIC 영역 끝-->
      </div>
    </v-col>
  </v-container>
</template>

<script>
export default {
  props: {
    //allUsers: Array,
  },
  methods: {
    link() {},
  },
  data() {
    return {
      overlay: false,
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
    };
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
