<template>
  <form class="ui large form">
    <p><input v-model="task.title" placeholder="Please add title here" /></p>
    <p>
      <textarea
        v-model="task.description"
        placeholder="Add Task description here"
      >
      </textarea>
    </p>
    <p>
      <users v-model="task.assigneeId"></users>
    </p>
    <button type="button" v-on:click="buttonClicked">Add Task</button>
    <!--  {{ task }} -->
  </form>
</template>

<script>
import Users from "./Users.vue";
export default {
  components: { Users },
  data: function () {
    return {
      task: {
        title: null,
        description: null,
        assigneeId: null,
      },
    };
  },
  methods: {
    buttonClicked: function () {
      this.$emit("submitdata", this.task);
    },
  },
};
</script>