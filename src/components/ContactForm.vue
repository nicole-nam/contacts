<template>
  <div>
    <h3>Contact Form</h3>
    <form v-on:submit.prevent="onSubmit">
      <label>First name</label>
      <input v-model="fname" type="text" placeholder="Your name..." required />
      <br />
      <label>Last name</label>
      <input
        v-model="lname"
        type="text"
        placeholder="Your last name..."
        required
      />
      <br />
      <label>Phone</label>
      <input
        v-model="phone"
        type="number"
        placeholder="Phone number..."
        required
      />
      <br />
      <label>Email</label>
      <input v-model="email" type="email" placeholder="Email..." required />
      <br />
      

      <p v-if="errors.length">
        <b>Please correct the following error(s):</b>
        <ul>
          <li v-for="(error, index) in errors" :key="index">{{ error }}</li>
        </ul>
      </p>


      <input type="submit" @click="onSubmit()" />
    </form>
  </div>

  <ContactCard :contacts="contacts" />
</template>

<script>
import ContactCard from "./ContactCard";
export default {
  components: {
    ContactCard,
  },
  data() {
    return {
      errors: [],
      contacts: [],
      fname: null,
      lname: null,
      phone: null,
      email: null,
    };
  },
  methods: {
    onSubmit() {
      this.checkForm();
    },
    checkForm() {
      this.errors = [];
      if (!this.validEmail(this.email)) {
        this.errors.push("Valid email required.");
      }else {
              
      if (this.fname && this.lname && this.phone && this.email) {
        this.contacts.push({
          fname: this.fname,
          lname: this.lname,
          phone: this.phone,
          email: this.email,
          isHidden: true,
        });
        this.fname = null;
        this.lname = null;
        this.phone = null;
        this.email = null;
      }
      }
    },
    validEmail: function (email) {
      var re =
        /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    },
  },
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

/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type="number"] {
  -moz-appearance: textfield;
}
</style>
