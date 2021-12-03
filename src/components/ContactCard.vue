<template>
  <div v-for="(item, index) in list" :key="index">
    <h2>{{ item.fname }} {{ item.lname }}</h2>
    <button @click="toggleDetail(index)">Show Detail</button>
    <div :class="{ hide: item.isHidden }">
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
    toggleDetail(index) {
      this.list[index].isHidden = !this.list[index].isHidden;
    },
  },
};
</script>

<style scoped>
.hide {
  display: none;
}
</style>
