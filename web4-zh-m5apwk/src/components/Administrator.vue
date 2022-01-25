<template>
  <div class="administrator">
    <h2>Név: {{ admin.name }}</h2>
    <p>Email: {{ admin.email }}</p>
    <div>Jogosultságok: {{ admin.permissions }}</div>
    <div>
      <button type="button" @click="modifyAdmin">Módosítás</button>
      <button type="button" @click="deleteAdmin">Törlés</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["admin"],
  methods: {
    modifyAdmin() {
      this.$emit("modifyAdmin", this.admin);
    },
    deleteAdmin() {
      this.$emit("deleteAdmin", this.admin);
    },
  },
};
</script>

<style>
</style>