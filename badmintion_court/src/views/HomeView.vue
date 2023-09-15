<template>
  
  <div>
        <div class="text-welcome" margin-top="5%">
            <h1>ยินดีต้อนรับ</h1>
        </div>
        <div class="text-welcome" margin-top="5%">
            <body1 class="text-pleaseLogin">โปรดเข้าสู่ระบบเพื่อจองสนามแบตมินตันกับเรา</body1>
        </div>
        <div class="div-button-login">
            <v-btn x-large class="button-login-homepage" color="#8B47FA">
                <Body2 class="text-login">เข้าสู่ระบบ</Body2>
            </v-btn>
        </div>
        <div class="div-if-regis">
            <body2 class="text--if-regis">----------- หากคุณยังไม่เป็นสมาชิก ------------</body2>
        </div>
        <div class="div-button-regis">
            <v-btn x-large class="button-regis-homepage" >
                <Body2 class="text-regis">สมัครสมาชิก</Body2>
            </v-btn>
        </div>
    </div>
  
</template>

<script>


export default {
  name: 'HomeView',

  
    
  }

</script>
<style>
.text-welcome {
    color: #8B47FA;
    width: 100;
    display: flex;
    justify-content: center;
    margin-top: 2%;
}

h1 {
    font-size: 64px;
}

.text-pleaseLogin {
    font-size: 20px;
    color: #333333;
}

.div-button-login {
    margin-top: 5%;
    display: flex;
    justify-content: center;

}

.text-login {
    color: #ffffff;
}
.div-if-regis{
    margin-top: 5%;
    display: flex;
    justify-content: center;
}
.text--if-regis{
    color: #7c7b7b;
}
.div-button-regis{
  display: flex;
    justify-content: center;
}

.button-regis-homepage{
  margin-top: 5%;
  border: 2px solid #8B47FA;



}
.text-regis{
  color: #8B47FA;
}
</style>