<template>
  <!-- Search bar with input and action buttons -->
  <div class="search-bar">
    <!-- Text input for search functionality -->
    <input type="text" placeholder="Search Post-It" />
    <!-- Button to clear the search input -->
    <button class="clear">Clear</button>
    <!-- Button to trigger modal for adding a new Post-It -->
    <button class="add" @click="openModal">Add Post-It</button>
  </div>
</template>

<script>
export default {
  methods: {
    openModal() {
      this.$emit("open");
    },
  },
};
</script>

<style scoped>
.search-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  background-color: #f5f5f5;
  border-bottom: 1px solid #e5e5e5;
}
.search-bar input {
  width: 100%;
  padding: 10px;
  border: 1px solid #e5e5e5;
  border-radius: 4px;
  outline: none;
}
.search-bar button {
  padding: 10px;
  border: 1px solid #e5e5e5;
  border-radius: 4px;
  outline: none;
  cursor: pointer;
  min-width: 100px;
}
.search-bar .clear {
  margin-right: 10px;
}
.search-bar .add {
  background-color: #4caf50;
  color: #fff;
}
</style>
