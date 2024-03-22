<template>
  <div>
    <h2>Thêm liên hệ</h2>
    <ContactFormAdd @submit:contact="addContact" />
    <p>{{ message }}</p>
  </div>
</template>

<script>
import ContactFormAdd from "@/components/ContactFormAdd.vue"; // Thay đổi từ ContactForm sang ContactFormAdd
import ContactService from "@/services/contact.service";

export default {
  name: 'addContact',
  components: {
    ContactFormAdd, // Sửa thành ContactFormAdd
  },
  data() {
    return {
      message: "",
    };
  },
  methods: {
    async addContact(data) {
      try {
        await ContactService.create(data);
        this.message = "Liên hệ được thêm thành công.";
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
