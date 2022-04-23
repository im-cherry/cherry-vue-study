# 09 Vuex

> vuex를 이용하여 글로벌하게 state를 관리하는 방법을 학습합니다.

<br/>

**vuex** 는 글로벌하게 state를 관리할 수 있도록 도와주는 상태 관리 라이브러리 입니다.

- state : 관리할 상태 값들
- getters : 밖으로 내보낼 값들 (실제 컴포넌트에서 가져가 사용할 값들)
- mutations : 실제 state가 변화되는 곳
- actions : mutations 을 일으키는 곳 (state 변화x)

컴포넌트에서 state를 가져오기 위해서는 getters 를 이용하고 state 에 변화를 주기 위해서는 actions 를 이용합니다.

```
$ npm i --save vuex
$ npm i --save vuex@3.4.0
```

- src/store.js

```javascript
import Vue from "vue";
import Vuex from "vuex";

Vue.use(Vuex);

export default new Vuex.Store({
  state: {
    counter: 0,
  },
  getters: {
    counter: (state) => state.counter,
  },
  mutations: {
    increment: (state) => state.counter + 1,
    decrement: (state) => state.counter + 1,
  },
  actions: {
      addCounter: context => context.commit("increment")
      subCounter: context => context.commit("decrement")
  },
});
```

- main.js

```javascript
import Vue from "vue";
import App from "./App.vue";
import store from "./store";

Vue.config.productionTip = false;

new Vue({
  store,
  render: (h) => h(App),
}).$mount("#app");
```

- components/Left.vue

```html
<template>
  <div>
    <button @click="subCounter">-</button>
    <button @click="addCounter">+</button>
  </div>
</template>

<script>
  import { mapActions } from "vuex";
  export default {
    name: "Left",
    methods: {
      ...mapActions(["addCounter", "subCounter"]),
    },
  };
</script>

<style></style>
```

- components/Right.vue

```html
<template>
  <div>value: {{ counter }}</div>
</template>

<script>
  import { mapGetters } from "vuex";
  export default {
    name: "Right",
    computed: {
      ...mapGetters(["counter"]),
    },
  };
</script>

<style></style>
```

- App.vue

```html
<template>
  <div>
    <Left />
    <Right />
  </div>
</template>

<script>
  import Left from "@/components/Left";
  import Right from "@/components/Right";

  export default {
    name: "app",
    components: {
      Left,
      Right,
    },
  };
</script>

<style></style>
```

<br />
<br />
