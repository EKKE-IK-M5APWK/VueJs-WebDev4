<template>
  <select v-model="user" @change="change">
    <option value="">Please Choose a User</option>
    <option v-for="user in users" :key="user.id" :value="user">
      {{ user.name }}
    </option>
  </select>
</template>

<script>
export default {
  props: ["value"],
  data() {
    return {
      user: this.value,
      users: [
        { id: 1, name: "Leanne Graham" },
        { id: 2, name: "Ervin Howell" },
        { id: 3, name: "Clementine Bauch" },
      ],
    };
  },
  methods: {
    change() {
      this.$emit("input", this.user);
    },
  },
};
</script>