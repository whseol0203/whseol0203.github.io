<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      color="#f5efe6"
      app dense fixed
    >
      <v-spacer />

      <v-toolbar-title>레쉽피</v-toolbar-title>

      <v-spacer />
      <v-spacer />
      <v-spacer />
      <v-spacer />

      <v-btn to="/login">로그아웃</v-btn>

      <v-spacer />

      <template v-slot:extension>
        <v-row>
          <v-spacer />
          <v-col>
            <v-btn to="/signup" style="width: 100%">레시피 게시판</v-btn>
          </v-col>
          <v-col>
            <v-btn to="/login" style="width: 100%">요리 사진 게시판</v-btn>
          </v-col>
          <v-col>
            <v-btn to="/login" style="width: 100%">마이페이지</v-btn>
          </v-col>
          <v-spacer />
        </v-row>
      </template>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>

    <v-footer
    color="#f5efe6"
    >
      <div>푸터 위치입니다아</div>
    </v-footer>
  </v-card>
</template>
