<template>

  <div  style="width:100%; height: 100%; display: flex; justify-content: center; align-items: center;">
    <Appbar />
    <div
      style="width:100%; height: 100%; display: flex; justify-content: center; align-items: center;"
    >
      <v-form
        ref="LoginForm"
        :lazy-validation="lazy"
        style="width: 100%; height:100%; display: flex; justify-content: center; align-items: center; "
      >
        <v-card
          style="border: 5px solid rgba(139, 71, 250, 0.34) ;
border-radius: 30px; width: 30%; height:auto; padding-bottom: 20px "
        >
          <div style="display: flex; justify-content: center; align-items: center;">
            <v-card-title style="font-size: 25px; color: #8B47FA;">เข้าสู่ระบบ</v-card-title>
          </div>
          <v-card-text>
            <!-- username -->
            <v-row dense>
              <v-col cols="12" align="start">
                <v-text-field
                  label="ชื่อผู้ใช้"
                  outlined
                  v-model="username"
                  :rules="Rules.usernameRules"
                ></v-text-field>
              </v-col>
            </v-row>

            <!-- password -->
            <v-row dense>
              <v-col cols="12" align="start">
                <v-text-field
                  label="รหัสผ่าน"
                  outlined
                  v-model="password"
                  :rules="Rules.passwordRules"
                ></v-text-field>
              </v-col>
            </v-row>
            <a
              class="text-addmin-login"
              @click="loginaddmin() "
              style="color: gray"
            >เข้าสู่ระบบสำหรับผู้ดูแล</a>
          </v-card-text>

          <v-card-actions>
            <v-btn block rounded color="#8B47FA" class="white--text" @click="login()">เข้าสู่ระบบ</v-btn>
          </v-card-actions>
        </v-card>
      </v-form>
    </div>
  </div>
</template>

<script>
import Appbar from "../components/Appbar.vue";
export default {
  name: "LoginPage",
  components: {
    Appbar
  },
  data() {
    return {
      lazy: false,
      username: "",
      password: "",
      Rules: {
        usernameRules: [v => !!v || "กรุณากรอกชื่อผู้ใช้งาน"],
        passwordRules: [v => !!v || "กรุณากรอกรหัสผ่าน"]
      }
    };
  },
  methods: {
    login() {
      localStorage.setItem("username", this.username);
      this.$EventBus.$emit("getUsername");
      this.$EventBus.$emit("checkLogin");
      this.$router.push({ path: "/" }).catch(() => {});
    },
    loginaddmin() {
      this.$router.push({ path: "/loginaddmin" }).catch(() => {});
    }
  }
};
</script>

<style>
.mx-auto {
  margin-top: 5%;
  border: 5px solid rgba(139, 71, 250, 0.34);
  display: flex;
  justify-content: center;
}
.text-addmin-login {
  display: flex;
  justify-content: right;
  color: gray;
  text-decoration: underline;
}
</style>