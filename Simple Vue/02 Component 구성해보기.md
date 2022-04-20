# 02 Component 구성해보기

> view를 구성하는 작은 조각들에 대해서 알아봅니다.

<br />

## 1. 들어가며

component 란 view를 구성하는 작은 조각들입니다.

<br />
<br />

## 2. 실습

vue component를 만들어 레이아웃을 구성해봅시다.

```
$ vue create page-layout
$ npm run serve
```

- App.vue

  ```html
  <template></template>

  <script>
    export default {
      name: "app",
      component: {},
    };
  </script>

  <style></style>
  ```

- components 폴더 안에 있는 `HelloWorld.vue` 제거하기

<br />
<br />

## 3. .vue 파일 구성 알아보기

vue 파일들은 자신만의 html(`<template>`), style(`<style>`), script(`<script>`)를 가지기 때문에, component 별로 독립된 환경을 가지고 개발할 수 있습니다.

- App.vue

  ```html
  <template>
    <div>
      <h1>Hello Vue!</h1>
    </div>
  </template>

  <script>
    export default {
      name: "app",
      component: {},
    };
  </script>

  <style></style>
  ```

<br />
<br />

## 4. Style 변경과 scope

vue 에서 `scoped` 옵션으로 component 의 style scope를 적용할 수 있습니다.

- App.vue

```html
<template>
  <div>
    <h1>Hello Vue!</h1>
  </div>
</template>

<script>
  export default {
    name: "app",
    component: {},
  };
</script>

<style scoped>
  h1 {
    color: #03a9f4;
  }
</style>
```

<br />
<br />

## 5. Component 생성하기

Layout을 구성하기 위해 component 폴더 안에 Header.vue, Menu.vue, Content.vue 를 생성합니다.

- [컴포넌트].vue

  ```html
  <template>
    <div>컴포넌트 이름</div>
  </template>

  <script>
    export default {};
  </script>

  <style scoped></style>
  ```

<br />
<br />

## 6. Component 가져오기

App.vue 에서 모든 컴포넌트들을 가져옵니다.

- App.vue

  ```
  <template>
  <div>
      <Header/>
      <div>
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
      components: {
      Header,
      Menu,
      Content,
      },
  };
  </script>

  <style scoped>
  </style>
  ```

<br />
<br />

## 7. style 적용하기

Component에 style을 적용합니다.

- App.vue

  ```
  <template>
  <div>
      <Header/>
      <div class="wrap">
          <Menu />
          <Content />
      </div>
  </div>
  </template>

  <style scoped>
      .wrap {
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
    export default {};
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
    export default {};
  </script>

  <style scoped>
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
    export default {};
  </script>

  <style scoped>
    div {
      flex: 2;
    }
  </style>
  ```

<br />
<br />

:arrow_forward:[03 State와 Props](./03%20State%EC%99%80%20Props.md):arrow_forward:
