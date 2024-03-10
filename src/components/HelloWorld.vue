<template>
  <div class="main">
    <button @click="(e) => increaseCounter(e, 123)">Increase</button>
    <span>{{ counter }}</span>
    <br />
    <br />
    <form action="" @submit.prevent="sendFormData" v-if="!isLogin">
      <label for="">Enter email</label>
      <input type="text" name="email" v-model="email" />
      <button type="submit">Login</button>
    </form>
    <div v-else>
      <button type="button" @click="(e) => (isLogin = false)">Logout</button>
      <br />
      <span>{{ isLogin ? "Đã đăng nhập" : "Chưa đăng nhập" }}</span>
      <br />
      <br />
      <h1>computed</h1>
      <p>Original message: "{{ message }}"</p>
      <p>Computed reversed message: "{{ reversedMessage }}"</p>
      <br />
      <br />
      <h1>Binding HTML Classes</h1>
      <div class="static" v-bind:class="classObject"></div>
    </div>
    <br />
    <br />
    <h1>List Rendering</h1>
    <ul>
      <li v-for="(skill, index) in listSkill" :key="index">
        {{ skill }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => {
    return {
      counter: 0,
      accountEmail: "xethongs100@gmail.com",
      email: "",
      isLogin: false,
      message: "Hello",
      isActive: true,
      isError: false,
      listSkill: [
        "Java",
        "PHP",
        "Javascript",
        "HTML5",
        "SQL",
        "Android",
        "iOS",
        "MySQL",
        "Tester",
        "English",
        "Ruby",
        "Python",
        "Ruby on Rails",
        "QA QC",
        "Database",
        ".NET",
        "Business Analyst",
        "NodeJS",
        "ReactJS",
        "Designer",
      ],
    };
  },
  props: {
    msg: String,
  },
  methods: {
    increaseCounter(e, number) {
      console.log("event", e);
      console.log("number", number);
      ++this.counter;
    },
    sendFormData() {
      this.isLogin = this.accountEmail === this.email ? true : false;
    },
  },
  computed: {
    reversedMessage() {
      // `this` points to the vm instance
      return this.message.split("").reverse().join("");
    },
    classObject() {
      return {
        active: this.isLogin,
        error: !this.isLogin,
      };
    },
  },
};
</script>

<style lang="css" scoped>
.static {
  height: 100px;
  width: 100px;
  background: green;
}

.static.active {
  background: blue;
}

.static.error {
  background: red;
}
</style>
