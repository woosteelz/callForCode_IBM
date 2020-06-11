<template>
  <v-container fluid grid-list-md>
    <v-row dense wrap justify="start" align="start">
      <v-col
        cols="12"
        v-for="card in cards"
        :key="cards.indexOf(card)"
        xs="12"
        sm="6"
        md="4"
        lg="3"
        x="12"
      >
        <v-hover>
          <template v-slot:default="{ hover }">
            <v-card
              @click="$router.push({ name: 'MainPage' })"
              class="mx-auto"
              max-width="300"
              max-height="350"
            >
              <div class="my-1">
                <v-img width="300" height="150" contain :src="card.src"></v-img>
              </div>
              <v-divider />
              <v-card-text>
                <h3 class="title primary--text my-2">{{ card.title }}</h3>
                {{ card.descript }}
                <v-text class="caption grey--text text--darken-2"
                  ><pre>{{ card.major }} / {{ card.minor }}</pre></v-text
                >
              </v-card-text>

              <v-fade-transition>
                <v-overlay v-if="hover" absolute color="grey"> </v-overlay>
              </v-fade-transition>
            </v-card>
          </template>
        </v-hover>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          title: "인하부고 농구 동아리",
          descript: "인하부고 농구 동아리입니다!",
          major: "스포츠",
          minor: "농구",
          src:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSq-h20zqWDYMWeSgIm1K40VWlfIz5oCzRATMzYm88gfKrEMCku&usqp=CAU",
        },
        {
          title: "우신고 천체관측 동아리",
          descript: "번개모임 다수",
          major: "과학",
          minor: "우주",
          src:
            "https://w.namu.la/s/46f46e4857a80fd2dfecb73eef27b0f084ccb49e12c409668ec7c6e34f7401f0fd4f77b00e58cfbb0f23c0dd704b0b5744cba255492ea433c9dc301087946fb314d5c821b4f1ba10a790c3a3bf967643f485f4c04d9692e4720d10a4993cba92",
        },
        {
          title: "부평고 독서 동아리",
          descript: "독서를 사랑하는 사람들의 모임입니다!",
          major: "문화",
          minor: "책",
          src:
            "https://ww.namu.la/s/9b66e90e52352e88380571740e19fd3a7e526d15e2762f8d1c3c84db23c37e5fb539b81cc97b66119daa63fd66b6a879342c238016430a7fe00ebdd25b34441d09617ecd6e023da9d2018b58d5b935a7a1fafba05a01cf6c2eacdc75c673c7e6764a024b3c62c861e4362528880c895b",
        },
        {
          title: "율천고 여행 동아리",
          descript: "당분간 방구석 여행을 지향합니다.",
          major: "문화",
          minor: "여행",
          src:
            "https://scontent-ssn1-1.xx.fbcdn.net/v/t31.0-8/1233190_1378539029042333_1105234693_o.jpg?_nc_cat=102&_nc_sid=09cbfe&_nc_ohc=CIDFVg4OJgkAX93Lgvo&_nc_ht=scontent-ssn1-1.xx&oh=2ea3ca0a267f4f93df3d635dcdd71ba7&oe=5F084DD5",
        },
        {
          title: "상명대 교육 봉사 동아리",
          descript: "봉사를 사랑하는 사람들의 모임입니다!",
          major: "사회",
          minor: "봉사",
          src:
            "https://w.namu.la/s/5e569d3575ecce1816920d09d831895ecaed09ecca70ba4860f3d1664becf3f8e7836c9c531dae30f65afa6742d26338df4c89a60dd5f001ef6152db239d3066a16ce0d4a8b9b26fbd10d289b74492c841fd55079ba5d4befbbdeb64e4a4ce396421cd431b39f575f46e055a2c655133",
        },
        {
          title: "BTS 모임",
          descript: "BTS관련 소식",
          major: "문화",
          minor: "노래",
          src:
            "https://upload.wikimedia.org/wikipedia/commons/f/ff/BTS_logo_%282017%29.png",
        },
      ],
      overlay: false,
    };
  },
};
</script>
