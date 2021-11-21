<template>
  <form class="addlist" @submit.prevent="addlList">
    <input
      v-model="title"
      class="text-input"
      placeholder="Add new.list"
      type="text"
    />
    <button type="submit" class="add-button">Add</button>
  </form>
</template>
<script>
export default {
  data: function () {
    return {
      title: "",
    };
  },
  methods: {
    addList: function () {
      this.$store.dispatch("addlist", {
        title: this.title,
      });
      this.title = "";
    },
  },
};
</script>
