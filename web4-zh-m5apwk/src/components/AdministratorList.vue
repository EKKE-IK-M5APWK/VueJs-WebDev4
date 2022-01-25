<template>
  <div class="administrator-list">
    <input-form @adminAdd="adminAdd"></input-form>
    <administrator
      v-for="(admin, index) in admins"
      :key="index"
      :admin="admin"
    ></administrator>
  </div>
</template>

<script>
import InputForm from "./InputForm.vue";
import Administrator from "./Administrator.vue";
export default {
  components: { Administrator, InputForm },
  data() {
    return {
      admins: [
        {
          id: 1,
          name: "Izabella",
          email: "test@test.com",
          permissions: ["UserManager"],
        },
      ],
    };
  },
  methods: {
    adminAdd(value) {
      value.id = this.admins.lenght + 1;
      this.admins.push(value);
    },
  },
};
</script>

<style>
</style>