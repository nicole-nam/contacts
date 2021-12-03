<template>
  <div>
    <h2>First name & last name</h2>
    <button @click="toggleDetail()">Show Detail</button>
    <div v-if="detailVisible">
      <p>Phone:</p>
      <p>Email:</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      detailVisible: false,
    };
  },
  methods: {
    toggleDetail() {
      this.detailVisible = !this.detailVisible;
      console.log(this.detailVisible);
    },
  },
};
</script>
