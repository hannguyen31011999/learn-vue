<template>
  <div class="header">
    <h1>{{ title }}</h1>
    <br />
    <br />
    <h1>Props and Custom Event Emit</h1>
    <button @click="() => changeTitle('This is title A')">
      Change Title A
    </button>
    <button @click="() => changeTitle('This is title B')">
      Change Title B
    </button>
    <button @click="handleChangeTitle()">Change Title Event Emit</button>
  </div>
</template>
<script>
export default {
  data: () => {
    return {};
  },
  props: {
    title: String,
    changeTitle: Function,
  },
  methods: {
    handleChangeTitle() {
      this.$emit("handleChangeTitleEvent", "This is title custom event");
    },
  },
};
</script>
