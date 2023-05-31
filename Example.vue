

<template>
  <div>
    <form @submit.prevent="submitForm">
      <!-- ฟอร์มข้อมูล -->
      <label for="name">Name:</label>
      <input type="text" id="name" v-model="formData.name">
      
      <label for="email">Email:</label>
      <input type="email" id="email" v-model="formData.email">
      
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      formData: {
        name: '',
        email: ''
      }
    };
  },
  methods: {
    async submitForm() {
      try {
        const response = await axios.post('https://example.com/api/data', this.formData);
        console.log(response.data); // แสดงข้อมูลที่ได้รับจากเซิร์ฟเวอร์
        
      } catch (error) {
        console.error(error); // แสดงข้อผิดพลาดที่เกิดขึ้น
        
      }
    }
  }
};
</script>

<style>
/* สไตล์ของคอมโพเนนต์ */
</style>
