# 04 v-for 를 이용한 리스트 렌더링

- App.vue

```
<template>
  <div id="app">
    <Webtoon :items="webtoos" />
  </div>
</template>

<script>
import Webtoon from "@/components/Webtoon"

export default {
  data() {
    return {
      webtoons: [
        {
          name: "햄스터와 그녀",
          link: "http://webtoon.daum.net/webtoon/view/hamsterandher",
          img:
            "http://t1.daumcdn.net/webtoon/op/478cdf37f585607982ffa9e35b432e8503be8a54"
        },
        {
          name: "프롬 스타",
          link: "http://webtoon.daum.net/webtoon/view/fromstar",
          img:
            "http://t1.daumcdn.net/webtoon/op/a7fb953d722c1130bfc18440f7e3ce448ece57a1"
        },
        {
          name: "위대한 로맨스",
          link: "http://webtoon.daum.net/webtoon/view/greatromance",
          img:
            "http://t1.daumcdn.net/webtoon/op/a816281cb4df5c50a20ac386fd6e496643d0f085"
        },
        {
          name: "빛나는 손을",
          link: "http://webtoon.daum.net/webtoon/view/Hand",
          img: "http://t1.daumcdn.net/cartoon/5913FCAC0234C50001"
        }
      ]
    };
  }
};
</script>
```

- Webtoon.vue

```html
<template>
  <div>
    <h2>Webtoon</h2>
    <ul class="wrap">
      <li class="item" v-for="(item, idx) in items" :key="{idx}">
        <a :href="item.link" targe="_blank">
          <img :src="item.img" />
          <span class="tit">제목: {{ item.name }}</span>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    props: {
      items: {
        type: Array,
        default: () => [],
      },
    },
  };
</script>

<style scoped>
  h2 {
    text-align: center;
  }

  a {
    list-style: none;
    text-decoration: none;
  }

  li {
    list-style: none;
  }

  .wrap {
    max-width: 450px;
    width: 100%;
    margin: 0 auto;
  }

  .item {
    border-bottom: 1px solid #ebebeb;
    margin-bottom: 25px;
  }

  .tit {
    display: inline-block;
    font-size: 18px;
    font-weight: bold;
    color: #000;
    padding: 20px 15px;
  }

  img {
    width: 100%;
    background: #ebebeb;
    border-radius: 4px;
  }
</style>
```

:arrow_forward:[05 v-if, v-show를 이용한 조건부 렌더링](./05%20v-if%2C%20v-show%20%EB%A5%BC%20%EC%9D%B4%EC%9A%A9%ED%95%9C%20%EC%A1%B0%EA%B1%B4%EB%B6%80%20%EB%A0%8C%EB%8D%94%EB%A7%81.md):arrow_forward:
