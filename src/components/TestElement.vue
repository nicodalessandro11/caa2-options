<template>
  <div>
    <h1 v-if="isOdd">I am odd</h1>
    <h1 v-else>I'm not an odd package</h1>
    <button class="btn" @click="sendPackage">Send packages</button>
  </div>
</template>

<script>
export default {
  props: {
    id: Number,
    items: Number,
    size: String,
    width: Number,
    available: Boolean,
  },
  data() {
    return {
      count: 0,
      values: [
        { id: 1, items: 3, size: "M", width: 90, available: false },
        { id: 2, items: 5, size: "L", width: 98, available: true },
      ],
    };
  },

  computed: {
    isOdd() {
      return this.count % 2 !== 0;
    },
  },

  methods: {
    increaseItemsCount(items) {
      if (items % 3 === 0) {
        this.count++;
      }
    },

    sendPackage() {
      this.values.forEach((item) => {
        this.increaseItemsCount(item.items);
      });
      alert(`Entregados ${this.count} artículos.`);
      console.log(this.count);
    },
  },
};
</script>

<style scoped></style>
