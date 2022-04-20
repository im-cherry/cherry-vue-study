# 01 vue-cli 알아보기

> vue project 환경에 대해서 학습합니다.

<br/>

## 1. VUE CLI 란?

vue-cli 는 기본 vue 개발 환경을 설정해주는 도구입니다.  
vue-cli 가 기본적인 프로젝트 세팅을 해주기 때문에 폴더 구조에 대한 고민, lint, build, 어떤 라이브러리로 구성을 해야되는지 webpack 설정은 어떻게 해야되는지에 대한 고민을 덜 수 있습니다.

_CLI(Command Line Interface) : 텍스트 터미널을 통해 사용자와 컴퓨터가 상호작용하는 방식_

<br/>

### 1) VUE-CLI 설치하기

```
$ npm install -g @vue/cli
$ yarn global add @vue/cli

$ vue --version
```

<br/>

### 2) VUE-CLI로 프로젝트 생성해보기

```
$ vue create [프로젝트명]
$ cd hello-vue
$ npm run serve
```

> **라이브러리**
>
> - [Babel](https://babeljs.io/)
> - [TypeScript](https://www.typescriptlang.org/)
> - [PWA(Progressive Web App)](https://web.dev/progressive-web-apps/)
> - [Router](https://router.vuejs.org/)
> - [Vuex](https://vuex.vuejs.org/)
> - [CSS Pre-processors](https://htmlmag.com/article/an-introduction-to-css-preprocessors-sass-less-stylus)
> - [Linter](https://eslint.org/) / [Formatter](https://github.com/prettier/prettier)
> - [Unit Testing](https://jestjs.io/)
> - [E2E Testing](https://www.cypress.io/)

<br/>
<br/>

:arrow_forward:[02 Component 구성해보기](./02%20Component%20%EA%B5%AC%EC%84%B1%ED%95%B4%EB%B3%B4%EA%B8%B0.md):arrow_forward:
