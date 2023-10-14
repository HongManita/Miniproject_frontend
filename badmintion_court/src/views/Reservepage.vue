<template>
  <div>
    <AppbarCust />
    <div class="text-table">
      <h2>ผลการจองสนาม</h2>
    </div>

    <div class="table-reserve">
    <v-simple-table fixed-header height="600px">
      <template v-slot:default>
        <thead class="table-head">
          <tr>
            <th class="text-center" style="font-size: 15px">วันที่จอง</th>
            <th class="text-center" style="font-size: 15px">เวลาจอง</th>
            <th class="text-center" style="font-size: 15px">สนาม</th>
         
          </tr>
        </thead>
      
      </template>
    </v-simple-table>
  </div>

  </div>
</template>
  <script>
import AppbarCust from "../components/AppbarCust.vue";
export default {
  name: "Reserve",
  components: {
    AppbarCust
  }
};
</script>
  
<style scoped>
.text-table {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 30px;
  color: rgb(110, 109, 109);
}
.table-reserve {

height: 550px;
margin-left: 100px;
margin-right: 100px;
margin-top: 40px;
}
</style>