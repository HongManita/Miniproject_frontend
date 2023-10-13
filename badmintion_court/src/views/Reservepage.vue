<template>
    <div
      style="height: 100%; width: 100%;  display: flex; justify-content: center; align-items: center;"
    >
       ssssssssssssssgdgdgd
    </div>
  </template>
  
  <script>
  export default {
    name: "LoginPage",
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
      loginaddmin(){
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
  .text-addmin-login{
    display: flex;
    justify-content: right;
    color: gray;
    text-decoration: underline
  }
  </style>