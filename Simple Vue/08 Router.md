# 08 Router

> vue-router를 이용하여 SPA routing 을 구현해봅시다.

<br />

```
$ npm i --save vue-router
$ npm i --save vue-router@2
```

- src/router.js

  ```javascript
  import Vue from "vue";
  import VueRouter from "vue-router";
  import ErrorPage from "./views/ErrorPage";
  import Home from "./views/Home";

  Vue.use(VueRouter);

  const router = new VueRouter({
    mode: "history",
    routes: [
      { path: "/", component: Home },
      { path: "*", component: ErrorPage },
    ],
  });

  export default router;
  ```

````

- src/views/Home.vue

    ```html
    <template>
    <div>
        <h1>Home Page</h1>
    </div>
    </template>

    <script>
    export default {};
    </script>

    <style></style>
    ```

- src/views/ErrorPage.vue

    ```html
    <template>
    <div>
        <h1>Error Page</h1>
    </div>
    </template>

    <script>
    export default {};
    </script>

    <style></style>
````

- src/main.js

  ```javascript
  import Vue from "vue";
  import App from "./App.vue";
  import router from "./router";

  Vue.config.productionTip = false;

  new Vue({
    router,
    render: (h) => h(App),
  }).$mound("#app");
  ```

- App.vue

  ```html
  <template>
    <div>
      <router-view />
    </div>
  </template>

  <script>
    export default {};
  </script>

  <style></style>
  ```

<br/>
<br/>

:arrow_forward:[09](./09%20Todo%20-%20%EC%A4%80%EB%B9%84.md):arrow_forward:
