# 05 v-if, v-show를 이용한 조건부 렌더링

> state 값에 따라 다르게 렌더링하는 방법을 학습합니다.

<br />

`v-if` 는 조건에 따라 컴포넌트가 실제로 제거되고 생성됩니다.

- App.vue

  ```html
  <template>
    <div>
      <div v-if="true">True</div>
      <div v-else>False</div>
    </div>
  </template>

  <script>
    export default {
      name: "app",
    };
  </script>

  <style scoped></style>
  ```

`v-show` 는 조건에 따라 css의 display 속성이 변경됩니다.

- App.vue

  ```html
  <template>
    <div>
      <div v-show="true">True</div>
      <div v-show="false">False</div>
    </div>
  </template>

  <script>
    export default {
      name: "app",
    };
  </script>

  <style scoped></style>
  ```

<br/>

:arrow_forward:[06 Data Binding](./06%20Data%20Binding.md):arrow_forward:
