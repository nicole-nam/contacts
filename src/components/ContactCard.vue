<template>
  <div v-for="(item, index) in list" :key="index">
    <h2>{{ item.fname }} {{ item.lname }}</h2>
    <button @click="toggleDetail()">Show Detail</button>
    <div v-if="detailVisible">
      <p><strong>Phone:</strong> {{ item.phone }}</p>
      <p><strong>Email:</strong> {{ item.email }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["contacts"],
  data() {
    return {
      list: this.contacts,
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
