<template>
  <div>
    <h3>Contact Form</h3>
    {{ contact }}
    <form v-on:submit.prevent="onSubmit">
      <label>First name</label>
      <input v-model="contact.fname" type="text" placeholder="Your name..." />
      <br />
      <label>Last name</label>
      <input
        v-model="contact.lname"
        type="text"
        placeholder="Your last name..."
      />
      <br />
      <label>Phone</label>
      <input
        v-model="contact.phone"
        type="number"
        placeholder="Phone number..."
      />
      <br />
      <label>Email</label>
      <input v-model="contact.email" type="email" placeholder="Email..." />
      <br />
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contact: {
        fname: null,
        lname: null,
        phone: null,
        email: null,
      },
    };
  },
  methods: {},
};
</script>

<style>
input[type="text"],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type="number"],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type="email"],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type="submit"] {
  width: 100%;
  background-color: #4caf50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: #45a049;
}

div {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>
