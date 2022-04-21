# 03 State와 Props

> 상태 관리에 대해서 알아봅니다.

<br/>

state와 props 는 component 가 데이터를 받거나 처리하고 보내기 위해 사용됩니다.  
state는 내부 컴포넌트에서 생성하고 활동하고, 데이터를 변경할 수 있습니다.  
props는 외부(부모) 컴포넌트에서 상속 받는 데이터이며, 데이터를 변경할 수 없습니다.  
vue에 관련한 무엇인가를 적용하기 위해서는 `v-bind` 라는 것을 이용합니다. (`v-bind:style`, `:style`, `:class`)

- Box.vue

  ```html
  <template>
    <div
      :class="['box', color]"
      :style="{ width: width + 'px', height: height + 'px'}"
    ></div>
  </template>

  <script>
    export default {
      props: {
        color: {
          type: String,
          default: "",
        },
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
    </div>
  </template>

  <script>
    import Box from "@/components/Box";
    export default {
      name: "app",
      components: {
        Box,
      },
    };
  </script>

  <style></style>
  ```

<br/>
<br/>

:arrow_forward:[04 v-for 를 이용한 리스트 렌더링](./04%20v-for%20%EB%A5%BC%20%EC%9D%B4%EC%9A%A9%ED%95%9C%20%EB%A6%AC%EC%8A%A4%ED%8A%B8%20%EB%A0%8C%EB%8D%94%EB%A7%81.md):arrow_forward:
