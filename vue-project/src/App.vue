<script>
  import AppHeader from "@/components/AppHeader.vue";
  import InputSearch from "./components/InputSearch.vue";
  import ContactList from "./components/ContactList.vue";
  import ContactCard from "./components/ContactCard.vue";
  
  export default {
    components: {
      AppHeader,
    },
  };
</script>

<template>
  <div id="app">
    <AppHeader />
    <div class="container mt-3">
      <div class="row">
        <div class="col-md-4">
          <InputSearch />
          <ContactList :contacts="contacts" :activeIndex="activeIndex" @update:activeIndex="updateActiveIndex" />
        </div>
        <div class="col-md-8">
          <ContactCard v-if="selectedContact" :contact="selectedContact" />
        </div>
      </div>
      <router-view /> <!-- Đây là nơi router sẽ render component -->
    </div>
  </div>
</template>


<style>
  .page {
    max-width: 800px;
    margin: auto;
  }
</style>
