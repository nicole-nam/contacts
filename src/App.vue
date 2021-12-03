<template>
  <ContactForm />
  <ContactCard />
</template>

<script>
import ContactCard from "./components/ContactCard";
import ContactForm from "./components/ContactForm";
export default {
  name: "app",
  components: {
    ContactCard,
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
