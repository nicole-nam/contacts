<template>
  <ContactForm />
</template>

<script>
import ContactForm from "./components/ContactForm";
export default {
  name: "app",
  components: {
    ContactForm,
  },
  data() {
    return {
      friends: [
        {
          fName: "Nicole",
          lName: "Nam",
          phone: "6474049660",
          email: "ejnam@gmail.com",
        },
      ],
    };
  },
};
</script>
