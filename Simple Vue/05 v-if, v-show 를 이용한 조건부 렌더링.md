# 05 v-if, v-show를 이용한 조건부 렌더링

`v-if` 조건에 따라 컴포넌트가 실제로 제거되고 생성된다.  
`v-show` 는 단순히 css의 display 속성만 변경된다.

- App.vue

```
<template>
    <div>
        <h2>Web</h2>
        <ul class="wrap">
            <li class="item" v-for="(item, idx) in items" :key="{idx}">
                <a :href="item.link" target="_blank">
                    <img :src="item.img" />
                    <span class="tit">제목 : {{item.name}}</span>
                </a>
                <span class="tag" v-if="item.isUpdate">N</span>
            </li>
        </ul>
    </div>
</template>

<script>
import Webtoon from "./components/Webtoon";

export default {
  components: {
    Webtoon
  },
  data() {
    return {
      webtoons: [
        {
          name: "햄스터와 그녀",
          link: "http://webtoon.daum.net/webtoon/view/hamsterandher",
          img:
            "http://t1.daumcdn.net/webtoon/op/478cdf37f585607982ffa9e35b432e8503be8a54",
          isUpdate: true
        },
        {
          name: "프롬 스타",
          link: "http://webtoon.daum.net/webtoon/view/fromstar",
          img:
            "http://t1.daumcdn.net/webtoon/op/a7fb953d722c1130bfc18440f7e3ce448ece57a1",
          isUpdate: true
        },
        {
          name: "위대한 로맨스",
          link: "http://webtoon.daum.net/webtoon/view/greatromance",
          img:
            "http://t1.daumcdn.net/webtoon/op/a816281cb4df5c50a20ac386fd6e496643d0f085",
          isUpdate: false
        },
        {
          name: "빛나는 손을",
          link: "http://webtoon.daum.net/webtoon/view/Hand",
          img: "http://t1.daumcdn.net/cartoon/5913FCAC0234C50001",
          isUpdate: false
        }
      ]
    };
  }
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
  position: relative;
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

.tag {
  position: absolute;
  left: 10px;
  top: 10px;
  padding: 5px 30px;
  color: #fff;
  border-radius: 4px;
  background: #fc2332;
  font-weight: bold;
}
</style>
```

:arrow_forward:[06 Data Binding](./06%20Data%20Binding.md):arrow_forward:
