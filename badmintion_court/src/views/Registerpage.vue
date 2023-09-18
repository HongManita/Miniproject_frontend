<template>
  <div
    style="height: 100%; width: 100%;  display: flex; justify-content: center; align-items: center;"
  >
    <v-form
      ref="LoginForm"
      :lazy-validation="lazy"
      style="width: 100%; height:100%; display: flex; justify-content: center; align-items: center;"
      @submit.prevent="registerCust()"
    >
      <v-card
        style="border: 5px solid rgba(139, 71, 250, 0.34) ;
border-radius: 30px; width: 30%; height:auto; "
      >
        <div style="display: flex; justify-content: center; align-items: center;">
          <v-card-title style="font-size: 25px; color: #8B47FA;">สมัครสมาชิก</v-card-title>
        </div>
        <v-container>
          <v-row>
            <v-col cols="12" md="6">
              <v-text-field
                v-model="firstname"
                :rules="Rules.firstnameRules"
                label="ชื่อ"
                required
                outlined
              ></v-text-field>
            </v-col>

            <v-col cols="12" md="6">
              <v-text-field
                v-model="lastname"
                :rules="Rules.lastnameRules"
                label="นามสกุล"
                required
                outlined
              ></v-text-field>
            </v-col>

            <v-col cols="12" md="12">
              <v-text-field
                v-model="tel"
                :rules="Rules.telRules"
                label="เบอร์โทรศัพท์"
                required
                outlined
              ></v-text-field>
            </v-col>

            <v-col cols="12" md="12">
              <v-text-field
                v-model="username"
                :rules="Rules.usernameRules"
                label="ชื่อผู้ใช้"
                required
                outlined
              ></v-text-field>
            </v-col>

            <v-col cols="12" md="12">
              <v-text-field
                v-model="password"
                :rules="Rules.passwordRules"
                label="รหัสผ่าน"
                required
                outlined
              ></v-text-field>
            </v-col>
          </v-row>
        </v-container>

        <v-card-actions>
          <v-btn
            block
            rounded
            color="#8B47FA"
            class="white--text"
            type="submit"
            @click="register()"
          >สมัครสมาชิก</v-btn>
        </v-card-actions>
      </v-card>
    </v-form>
  </div>
</template>

<script>
import { request } from "../../axios-config";
import Swal from "sweetalert2";
export default {
  name: "RegisPage",
  data() {
    return {
      lazy: false,
      firstname: "",
      lastname: "",
      tel: "",
      username: "",
      password: "",

      Rules: {
        usernameRules: [v => !!v || "กรุณากรอกชื่อผู้ใช้งาน"],
        passwordRules: [v => !!v || "กรุณากรอกรหัสผ่าน"],
        firstnameRules: [v => !!v || "กรุณากรอกชื่อ"],
        lastnameRules: [v => !!v || "กรุณากรอกนามสกุล"],
        telRules: [v => !!v || "กรุณากรอกเบอร์โทรศัพท์"]
      }
    };
  },
  methods: {
    register() {
      this.$router.push({ path: "/login" });
    }
  },
  async registerCust() {
    try {
      const data = new FormData();
      data.append(
        "body",
        JSON.stringify({
          firstname: this.firstname,
          lastname: this.lastname,
          tel: this.tel,
          username: this.username,
          password: this.password
        })
      );

      const response = await request.post("/customer", data, {
        headers: {
          "Content-Type": "multipart/form-data"
        }
      });
      if (response.status === 201) {
        Swal.fire({
          title: "success!",
          icon: "success",
          confirmButtonText: "Comfirm",
          timer: 1000
        });
        this.$router.push("/login");
      }
    } catch (error) {
      Swal.fire({
        title: "Wrong!",
        text: "Can not register",
        icon: "error",
        confirmButtonText: "confirm",
        timer: 1000
      });

      console.error("Error data:", error);
    }
  }
};
</script>
<style scoped>
</style>