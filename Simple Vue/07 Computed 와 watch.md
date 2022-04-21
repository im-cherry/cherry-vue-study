# 06 Computed 와 watch

computed : 연산 결과를 캐싱

- App.vue

  ```html
  <template>
    <div id="app">
      {{ message }}
      <h2>뒤집힌 message</h2>
      {{ reservedMessage }}
    </div>
  </template>

  <script>
    export default {
      name: "app",
      data() {
        return {
          message: "Hello Vue!!",
        };
      },
      computed: {
        reservedMessage() {
          return this.message.split("").reverse().join("");
        },
      },
    };
  </script>

  <style></style>
  ```

<br />

watch : state나 props를 감시하고 해당 값이 변경 되었을 때의 행동을 지정

- App.vue

  ```html
  <template>
    <div id="app">
      <input v-model="firstName" />
      <input v-model="lastName" />

      <h2>full name</h2>
      <span>{{ fullName }}</span>
    </div>
  </template>

  <script>
    export default {
      name: "app",
      data() {
        return {
          firstName: "",
          lastName: "",
          fullName: "",
        };
      },
      watch: {
        firstName(val) {
          this.fullName = `${val} ${this.lastName}`;
        },
        lastName(val) {
          this.fullName = `${this.firstName} ${val}`;
        },
      },
      // computed: {
      // fullName() {
      // return `${this.firstName} ${this.lastName}`;
      // },
      // },
    };
  </script>

  <style></style>
  ```

<br />

watch 는 언제 변하는지 예측이 어려울 때 많이 사용됩니다. (ex 비동기 통신)  
computed 는 복잡한 연산같은 것을 캐싱 처리하기 위해 사용됩니다.

<br/>
<br/>

:arrow_forward:[08 Router](./08%20Router.md):arrow_forward:
