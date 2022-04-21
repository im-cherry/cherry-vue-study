# 06 Data Binding

> 양방향 데이터 바인딩에 대해 학습합니다.

<br />

`v-model` 은 양방향 데이터 바인딩을 지원합니다.

- App.vue (text)

  ```html
  <template>
    <div>
      <h1>{{ title }}</h1>
      <input type="text" v-model="title" />
    </div>
  </template>

  <script>
    export default {
      name: "app",
      data() {
        title: "",
      },
    };
  </script>

  <style></style>
  ```

- App.vue (checkbox)

  ```html
  <template>
    <div>
      <h2>웹툰</h2>
      <input
        type="checkbox"
        id="프롬스타"
        value="프롬스타"
        v-model="checkedWebtoons"
      />
      <label for="프롬스타">프롬스타</label>
      <input
        type="checkbox"
        id="햄스터와그녀"
        value="햄스터와그녀"
        v-model="checkedWebtoons"
      />
      <label for="햄스터와그녀">햄스터와그녀</label>
      <input
        type="checkbox"
        id="위대한로맨스"
        value="프롬위대한로맨스스타"
        v-model="checkedWebtoons"
      />
      <label for="위대한로맨스">위대한로맨스</label>
      <br />
      <span>찜한 웹툰 : {{ checkedWebtoons }}</span>
    </div>
  </template>

  <script>
    export default {
      name: "app",
      data() {
        checkedWebtoons: [],
      },
    };
  </script>

  <style></style>
  ```

- App.vue (radio)

  ```html
  <template>
    <div>
      <h2>gender</h2>
      <input type="radio" id="male" value="male" v-model="gender" />
      <label for="male">남</label>
      <input type="radio" id="female" value="female" v-model="gender" />
      <label for="female">남</label>
      <br />
      <br />
      <span>당신의 성별을 알려주세요 : {{ gender }}</span>
    </div>
  </template>

  <script>
    export default {
      name: "app",
      data() {
        gender: "",
      },
    };
  </script>

  <style></style>
  ```

- App.vue (select)

  ```html
  <template>
    <div>
      <h2>선호 장르</h2>
      <select v-model="category">
        <option disabled value>선택해주세요</option>
        <option>로맨스</option>
        <option>호러</option>
        <option>스릴러</option>
      </select>
      <span>선택 : {{ category }}</span>
    </div>
  </template>

  <script>
    export default {
      name: "app",
      data() {
        category: "";
      },
    };
  </script>

  <style></style>
  ```

<br/>
<br/>

:arrow_forward:[07 Computed와 watch](./07%20Computed%20%EC%99%80%20watch.md):arrow_forward:
