<template>
  <form id="form" @submit.prevent="submitData">
    <div>
      <label>Name</label>
      <input type="text" v-model="nameInput" />
    </div>
    <div>
      <label>Email</label>
      <input type="mail" v-model="emailInput" />
    </div>
    <div>
      <label>Phone Number</label>
      <input type="number" v-model="phoneInput" />
    </div>
    <div>
      <button>Add Friend</button>
    </div>
  </form>
</template>

<script>
export default {
  emits: ["add-contact"],
  data() {
    return {
      nameInput: "",
      phoneInput: "",
      emailInput: "",
    };
  },
  methods: {
    submitData() {
      this.$emit(
        "add-contact",
        this.nameInput,
        this.phoneInput,
        this.emailInput
      );

      this.nameInput = "";
      this.phoneInput = "";
      this.emailInput = "";
    },
  },
};
</script>

<style>
#form {
  display: flex;
  flex-direction: column;
  align-items: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: auto;
  max-width: 30rem;
  width: 90%;
  padding: 2rem 0;
}

#form label {
  display: block;
}
#form > div {
  margin-top: 1rem;
}
</style>
