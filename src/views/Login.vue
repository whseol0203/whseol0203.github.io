<template>
  <v-container>
    <v-form ref="form">
      <v-row>
        <v-col cols="4" offset="4">
          <v-card-title style="justify-content: center">로그인</v-card-title>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="6" offset="3">
          <v-divider></v-divider>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="4" offset="4">
          <v-text-field v-model="info.id" label="id"></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="4" offset="4">
          <v-text-field v-model="info.pw" label="password"></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="3" offset="4">
          <v-checkbox v-model="info.al" label="자동 로그인"></v-checkbox>
        </v-col>
      </v-row>
      <v-row justify="center">
        <v-col cols="auto">
          <v-btn to="/email-auth">회원가입</v-btn>
        </v-col>
        <v-col cols="2">
          <v-btn @click="login" style="width: 100%">login</v-btn>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="6" offset="3">
          <v-divider></v-divider>
        </v-col>
      </v-row>

    </v-form>
  </v-container>
</template>

<script>
import herokuAPI from '@/api/heroku.js';

export default {
  data() {
    return {
      info: {
        id: null,
        pw: null,
        al: false
      }
    }
  },
  methods: {
    login() {
      const loginInfo = JSON.stringify({
        "nickname": null,
        "uid": this.info.id,
        "password": this.info.pw,
        "email": null,
        "auto_login": this.info.al,
      });
      console.log(loginInfo);
      herokuAPI.login(loginInfo)
        .then(function (response) {
          console.log("login", response);
          if(res.status == 200) {
            this.$router.push('/home')
          }
        }) 
        .catch(function (e) {
          console.log(e);
        });
    }
  }
}
</script>