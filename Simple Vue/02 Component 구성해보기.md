# 02 Component 구성해보기

> view를 구성하는 작은 조각들에 대해서 알아봅니다.

<br />

vue 파일들은 자신만의 html(`<template>`), style(`<style>`), script(`<script>`)를 가지기 때문에, component 별로 독립된 환경을 가지고 개발할 수 있습니다.  
component란 view를 구성하는 작은 조각들입니다.  
vue component 를 만들어 레이아웃을 구성해 봅시다. 레이아웃을 구성하기 위해 component 폴더 안에 vue 파일을 생성합니다.

- App.vue

  ```
  <template>
    <div>
      <Header />
      <div class="wrap">
        <Menu />
        <Content />
      </div>
    </div>
  </template>

  <script>
    import Header from "@/components/Header";
    import Menu from "@/components/Menu";
    import Content from "@/components/Content";

    export default {
      name: "app",
      component: {
        Header,
        Menu,
        Content,
      },
    };
  </script>

  <style scoped>
    .warp {
      display: flex;
    }
  </style>
  ```

- Header.vue

  ```html
  <template>
    <div>Header Component</div>
  </template>

  <script>
    export default {
      name: "header",
    };
  </script>

  <style scoped>
    div {
      position: sticky;
      height: 50px;
      border-bottom: 1px solid #ebebeb;
    }
  </style>
  ```

- Menu.vue

  ```html
  <template>
    <div>Menu Component</div>
  </template>

  <script>
    export default {
      name: "menu",
    };
  </script>

  <style>
    div {
      flex: 1;
    }
  </style>
  ```

- Content.vue

  ```html
  <template>
    <div>Content Component</div>
  </template>

  <script>
    export default {
      name: "content",
    };
  </script>

  <style>
    div {
      flex: 2;
    }
  </style>
  ```

<br />
<br />

:arrow_forward:[03 State와 Props](./03%20State%EC%99%80%20Props.md):arrow_forward:
