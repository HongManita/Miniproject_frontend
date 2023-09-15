<template>
    <v-form ref="form" >
    <v-card width="50%" height="100%">
      <v-card-title>เข้าสู่ระบบ</v-card-title>
      <v-card-text>
        <!-- username -->
        <v-row dense>
          <v-col cols="12" align="start">
            <v-text-field
            label="Outlined"
            outlined
          ></v-text-field>
          </v-col>
        </v-row>
     
        <!-- password -->
        <v-row dense>
          <v-col cols="12" align="start">
            <v-text-field
            label="Outlined"
            outlined
          ></v-text-field>
          </v-col>
        </v-row>
      </v-card-text>
    
      <v-card-actions>
        <v-btn
        
          block
          rounded
          color="success"
          class="white--text"
          
          >เข้าสู่ระบบ</v-btn
        >
      </v-card-actions>
    </v-card>
  </v-form>
</template>
<style>
.mx-auto {
    margin-top: 5%;
    border: 5px solid rgba(139, 71, 250, 0.34);
    display: flex;
    justify-content: center;
}
</style>