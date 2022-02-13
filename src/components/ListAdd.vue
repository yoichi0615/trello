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
  props: {
    title: {
      type: String,
      required: true
    },
    listIndex: {
      type: Number,
      required: true
    }
  },
  methods: {
    removeList: function() {
      if(confirm('本当にこのリストを削除しますか？')){
        this.$store.dispatch('removelist', { listIndex: this.listIndex })
      }
    },
  }
}
</script>
