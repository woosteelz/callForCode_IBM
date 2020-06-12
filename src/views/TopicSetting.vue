<template>
  <v-container>
    <v-col cols="9">
      <div class="page-body">
        <div class="story pb-1">
          <div class="pa-3">
            <h1>Weekly Topic Setting</h1>
          </div>

          <div class="pa-5">
            <h2>Post Weekly Topic</h2>
          </div>

          <div class="px-5">
            <v-text-field
              label="Input Weekly Topic"
              hide-details="auto"
            ></v-text-field>
          </div>

          <div class="pa-3" align="end">
            <v-btn color="blue" class="white--text">Submit</v-btn>
          </div>

          <div class="pt-5 px-5 d-flex justify-end">
            <h2>Recommend Topics</h2>
            <v-spacer />
            <div class="px-5">
              <v-text-field small outlined></v-text-field>
            </div>
            <div class="pt-5">
              <v-btn color="blue" class="white--text" small @click="getData()">
                submit
              </v-btn>
            </div>
          </div>

          <v-treeview selectable :items="items" dense></v-treeview>

          <div class="px-5 pt-5 d-flex justify-end">
            <h2>Auto Recommend</h2>
            <v-spacer></v-spacer>
            <div class="pb-3">
              <v-switch></v-switch>
            </div>
          </div>
          <div class="text--disabled pl-5">
            *해당 항목을 활성화하게 되면 뉴스 토픽이 매주 자동으로
            업데이트됩니다!
          </div>
        </div>
      </div>
    </v-col>
  </v-container>
</template>

<script>
import axios from "axios";

export default {
  data: () => ({
    DataString: null,
    selectionType: "leaf",
    selection: [],
    items: [
      {
        id: 1,
        name: "스포츠",
        children: [
          { id: 2, name: "농구" },
          { id: 3, name: "축구" },
          { id: 4, name: "배구" },
        ],
      },
      {
        id: 5,
        name: "여가",
        children: [
          { id: 6, name: "여행" },
          { id: 7, name: "독서" },
          { id: 8, name: "영화" },
        ],
      },
    ],
  }),
  methods: {
    getData() {
      axios
        .get("http://169.63.212.7:8000/api/public")
        .then((res) => {
          this.DataString = res.data;
          console.log(this.DataString);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
