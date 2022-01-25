<template>
  <div class="input-form">
    <form action="">
      <p>
        <input
          v-model="admin.name"
          ref="name"
          placeholder="Kérem adja meg a nevét!"
        />
      </p>
      <p>
        <input
          v-model="admin.email"
          ref="email"
          placeholder="Kérem adja meg az email címét!"
        />
      </p>
      <input
        type="checkbox"
        id="UserManager"
        value="UserManager"
        v-model="admin.checkedPermissions"
      />
      <label for="UserManager">UserManager</label>
      <input
        type="checkbox"
        id="Editor"
        value="Editor"
        v-model="admin.checkedPermissions"
      />
      <label for="Editor">Editor</label>
      <input
        type="checkbox"
        id="SystemManager"
        value="SystemManager"
        v-model="admin.checkedPermissions"
      />
      <label for="SystemManager">SystemManager</label>
      <input
        type="checkbox"
        id="SuperAdmin"
        value="SuperAdmin"
        v-model="admin.checkedPermissions"
      />
      <label for="SuperAdmin">SuperAdmin</label>
      <p>
        <button type="button" @click="buttonClicked">Admin hozzáadása</button>
      </p>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      permissions: ["UserManager", "Editor", "SystemManager", "SuperAdmin"],
      admin: {
        id: "null",
        name: "",
        email: "",
        checkedPermissions: [],
      },
    };
  },
  methods: {
    buttonClicked: function () {
      if (this.admin.name == "" || this.admin.name <= this.admin.name.length) {
        alert("Hibás név megadás!");
      } else {
        this.$emit("adminAdd", this.admin);
        /* resetInput(); */
      }
    },
    resetInput: function () {
      this.$refs["name"] = "";
      this.$refs["email"] = "";
    },
  },
};
</script>

<style>
</style>