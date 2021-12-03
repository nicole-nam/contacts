<template>
  <h3 class="padding">Contact List</h3>
  <div v-for="(item, index) in list" :key="index" class="flex">
    <div class="card">
      <h2>{{ item.fname }} {{ item.lname }}</h2>
      <button class="btn" @click="toggleDetail(index)">Show Detail</button>
      <div :class="{ hide: item.isHidden }">
        <p><strong>Phone:</strong> {{ item.phone }}</p>
        <p><strong>Email:</strong> {{ item.email }}</p>
      </div>
    </div>
    <div class="cssCircle minusSign" style="padding-top: 00px">&#8211;</div>
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
.flex {
  display: flex;
  align-items: center;
}
.padding {
  padding: 20px;
}
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 40%;
  margin: auto;
}
.btn {
  width: 100%;
  background-color: #4caf50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.cssCircle {
  -webkit-border-radius: 999px;
  -moz-border-radius: 999px;
  border-radius: 999px;

  width: 13px;
  height: 13px;
  padding: 0px;

  background: #4caf50;
  color: #fff;
  text-align: center;
  -webkit-transition: background 0.2s linear;
  -moz-transition: background 0.2s linear;
  -ms-transition: background 0.2s linear;
  -o-transition: background 0.2s linear;
  transition: background 0.2s linear;
  transition: color 0.2s linear;

  font: 13px Arial, sans-serif;
}

.cssCircle:hover {
  background: #45a049;
  cursor: pointer;
}

.minusSign {
  line-height: 0.9em;
  margin-bottom: 1px;
}

.minusSign:hover {
  color: white;
}
</style>
