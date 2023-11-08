<template>
  <div class="postit-list">
    <PostIt
      v-for="postIt in postItProp"
      :key="postIt.id"
      :title="postIt.title"
      :image="postIt.image"
      :date="postIt.date"
      :time="postIt.time"
      :dueDate="postIt.dueDate"
      :dueTime="postIt.dueTime"
      :priority="postIt.priority"
      :content="postIt.content"
      :featured="postIt.featured"
      :labels="postIt.labels"
    />
  </div>
</template>

<script>
import PostIt from "./PostIt.vue";
export default {
  components: {
    PostIt,
  },
  props: {
    postItProp: Array,
  },
};
</script>

<style scoped>
.postit-list {
  display: grid;
  width: 100%;
  grid-template-columns: 1fr 1fr 1fr;
}
</style>
