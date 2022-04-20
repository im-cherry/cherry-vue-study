# 03 State와 Props

> 상태 관리에 대해서 알아봅니다.

<br/>

vue는 document에 직접적인 접근을 하여 DOM을 제어하지 않습니다.  
state 라는 상태를 이용하여 DOM을 관리합니다.

<br/>

## 1. State

component의 state는 data라는 함수를 이용하여 구성할 수 있습니다.

- Box.vue

  ```html
  <script>
    export default {
      data() {
        return {
          width: 40,
          height: 80,
        };
      },
    };
  </script>
  ```

<br/>
<br/>

## 2. State를 이용하여 Style 적용하기

vue에 관련한 무엇인가를 적용하기 위해서는 `v-bind` 라는 것을 이용해야 합니다.  
html tag에 인라인으로 스타일을 적용할 때는 `v-bind:style` 또는 `v-bind` 를 생략한 `:style` 을 이용합니다.

props 나 state를 바탕으로 class를 적용해주기 위해서는 `v-bind:class`를 이용합니다.

- Box.vue

  ```html
  <template>
    <div
      v-bind:class="['box', color]"
      v-bind:style="{width: width + 'px', height: height + 'px'}"
    ></div>
  </template>

  <script>
    export default {
      props: {
        color: { type: String, default: "" },
      },
      data() {
        return {
          width: 40,
          height: 80,
        };
      },
    };
  </script>

  <style scoped>
    .box {
      border: 1px solid #000;
    }
    .blue {
      background: #009bff;
    }
    .purple {
      background: #8f46ff;
    }
    .green {
      background: #00bcac;
    }
  </style>
  ```

- App.vue

```html
<template>
  <div>
    <Box color="blue" />
    <Box color="purple" />
    <Box color="green" />
    <Box color="blue" />
    <Box color="purple" />
    <Box />
  </div>
</template>
```

<br/>
<br/>

## 4. Props

- App.vue

```html

```

<br/>
<br/>

## 5. Props를 바탕으로 class bind 해보기

<br/>
<br/>

:arrow_forward:[04 v-for 를 이용한 리스트 렌더링](./04%20v-for%20%EB%A5%BC%20%EC%9D%B4%EC%9A%A9%ED%95%9C%20%EB%A6%AC%EC%8A%A4%ED%8A%B8%20%EB%A0%8C%EB%8D%94%EB%A7%81.md):arrow_forward:
