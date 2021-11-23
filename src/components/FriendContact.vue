<template>
  <li>
    <h3>{{ name }} {{ isFavourit ? "(favourite)" : "" }}</h3>
    <button @click="toggleDetail">
      {{ detailsAreVisible ? "Hide" : "Show" }} Details
    </button>
    <button @click="toggleFav">Toggle favourite</button>
    <ul v-if="detailsAreVisible">
      <li><strong>Email: </strong>{{ emailAddress }}</li>
      <li><strong>Phone: </strong>{{ phoneNumber }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: Number,
      required: true,
    },
    emailAddress: {
      type: String,
      required: true,
    },
    isFavourit: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  // emits: ["toggle-favourite"],
  emits: {
    "toggle-favourite": function (id) {
      if (id) {
        return true;
      } else {
        console.log("id is missing");
        return false;
      }
    },
  },
  data() {
    return {
      detailsAreVisible: false,
    };
  },

  methods: {
    toggleDetail() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFav() {
      // custom event
      this.$emit("toggle-favourite", this.id);
    },
  },
};
</script>
