<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <HeaderComponent
      v-bind:title="titleHeader"
      v-bind:change-title="handleChangeTitle"
      v-on:handleChangeTitleEvent="handleChangeTitleEvent"
    />
    <button @click="handleChangeTitle('This is Header')">
      Change Title Default
    </button>
    <DemoRefComponent />
    <DemoSlotComponent>
      <h1>1234</h1>
      <button>abc</button>
    </DemoSlotComponent>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import HeaderComponent from "./components/HeaderComponent.vue";
import DemoRefComponent from "./components/DemoRefComponent.vue";
import DemoSlotComponent from "./components/DemoSlotComponent.vue";

export default {
  name: "App",
  components: {
    DemoRefComponent,
    HelloWorld,
    HeaderComponent,
    DemoSlotComponent,
  },
  data: () => {
    return {
      titleHeader: "This is Header",
    };
  },
  methods: {
    handleChangeTitle(title) {
      this.titleHeader = title;
    },
    handleChangeTitleEvent(title) {
      this.titleHeader = title;
    },
  },
  // lifecycle methods
  beforeCreate() {
    console.log("beforeCreate");
  },
  created() {
    console.log("created");
  },
  beforeMount() {
    console.log("beforeMount");
  },
  mounted() {
    console.log("mounted");
  },
  beforeUpdate() {
    console.log("beforeUpdate trigger change titleHeader", this.titleHeader);
  },
  updated() {
    console.log("updated trigger change titleHeader", this.titleHeader);
  },
  beforeDestroy() {
    console.log("beforeDestroy");
  },
  destroyed() {
    console.log("destroyed");
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
./components/DemoRefComponent.vue
