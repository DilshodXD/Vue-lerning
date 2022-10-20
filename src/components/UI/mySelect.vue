<template>
  <select v-model="modalValue" @change="changeOption" class="form-control">
    <option disabled value="">Category</option>
    <option v-for="option in options" :key="option.value" :value="options.value">
      {{ option.name }}
    </option>
  </select>
</template>

<script>
export default {
  name: "my-select",
  props: {
    modalValue: {
      type: String,
    },
    options: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    changeOption(e) {
        this.$emit("update:modalValue", e.target.value());
    },
  },
};
</script>