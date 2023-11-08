<template>
  <div class="main">
    <header class="header">
      <div class="header__left">
        <img src="./assets/uoc-logo.png" class="logo" alt="UOC Logo" />
        <span class="title">Post It Manager</span>
      </div>
    </header>
    <div class="content">
      <SearchBar @open="toggleModal" />
      <FilterBar />
      <main class="main">
        <PostItList :postItProp="postItArray" />
      </main>
      <ModalLayer v-if="showModal" @close="toggleModal">
        <template v-slot:header> Add New Post-It </template>
        <template v-slot:body>
          <PostItForm @submit="handleSubmit" />
        </template>
      </ModalLayer>
    </div>
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar.vue";
import FilterBar from "./components/FilterBar.vue";
import PostItList from "./components/PostItList.vue";
import PostItForm from "./components/PostItForm.vue";
import ModalLayer from "./components/ModalLayer.vue";

export default {
  components: {
    SearchBar,
    FilterBar,
    PostItList,
    PostItForm,
    ModalLayer,
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    handleSubmit() {
      this.toggleModal();
    },
  },
  data() {
    return {
      showModal: false,
      postItArray: [
        {
          id: 1,
          title: "Important Meeting",
          image:
            "https://img.freepik.com/foto-gratis/mujer-morena-escribiendo-correo-electronico-computadora-portatil-mientras-sentado-su-casa-enfoque-selectivo-mano_171337-13093.jpg?w=996&t=st=1698849440~exp=1698850040~hmac=0b0645298ac89448f5c811d41d5c580d1bd4846bed53e95d0db0b4bb4f31406dg",
          date: "2023-10-30",
          time: "09:00 AM",
          dueDate: "2023-11-15",
          priority: "high",
          content: "Prepare for the quarterly review meeting with the team.",
          labels: ["Work", "Meeting", "Urgent"],
          featured: true,
        },
        {
          id: 2,
          title: "Grocery List",
          image:
            "https://img.freepik.com/foto-gratis/mujer-morena-escribiendo-correo-electronico-computadora-portatil-mientras-sentado-su-casa-enfoque-selectivo-mano_171337-13093.jpg?w=996&t=st=1698849440~exp=1698850040~hmac=0b0645298ac89448f5c811d41d5c580d1bd4846bed53e95d0db0b4bb4f31406d",
          date: "2023-10-30",
          time: "10:00 AM",
          dueDate: "2023-10-31",
          priority: "medium",
          content:
            "Buy groceries for the week: milk, eggs, bread, and vegetables.",
          labels: ["Personal", "Groceries"],
          featured: false,
        },
        {
          id: 3,
          title: "Project Deadline",
          image:
            "https://img.freepik.com/foto-gratis/mujer-morena-escribiendo-correo-electronico-computadora-portatil-mientras-sentado-su-casa-enfoque-selectivo-mano_171337-13093.jpg?w=996&t=st=1698849440~exp=1698850040~hmac=0b0645298ac89448f5c811d41d5c580d1bd4846bed53e95d0db0b4bb4f31406d",
          date: "2023-10-31",
          time: "02:00 PM",
          dueDate: "2023-11-10",
          priority: "high",
          content:
            "Finish the project report and submit it before the deadline.",
          labels: ["Work", "Project", "Urgent"],
          featured: false,
        },
      ],
    };
  },
};
</script>

<style scoped>
body {
  padding: 0;
  margin: 0;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
  background-color: #f5f5f5;
  border-bottom: 1px solid #e5e5e5;
}
.header__left {
  display: flex;
  align-items: center;
}
.logo {
  height: 40px;
  margin-right: 10px;
}
.title {
  font-size: 24px;
  font-weight: 400;
}
</style>
