<!-- 기본 생성으로 호출된 스크립트
script setup 안에서는 export default를 할 수 없었음 -->
<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<!-- 새로 만든 스크립트 -->
<script>
/* 뷰 앱에서 쓸 데이터(리액트의 state)를 생성하고 내보냄 */
export default {
  data() {
    return {
      count: 0,
      titleClass: 'title'
    }
  },
  /* 호출하고 실행할 메서드를 정의, state를 조작할 수 있다. */
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>

<template>
  <header>
    <!-- css class를 동적으로 준 것은 아님,
    count 데이터는 동적으로 변경 -->
    <h1 :class="titleClass">{{count}}</h1>
    <p>vue로 확인하는 웹페이지 입니다. 아래 버튼을 누르면 값이 1씩 증가합니다</p>
    <!-- 증가 메서드와 함께 작성한 버튼 -->
    <button @click="increment">+1</button>
  </header>

  <RouterView />
</template>

<style scoped>
.title {
  color: red;
  font-weight: bolder;
}
</style>
