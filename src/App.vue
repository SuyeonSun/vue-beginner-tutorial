<template>
  <div>
    <h1> 반응형 refs </h1>
    <p> 독립적인 원시 값(예를 들어, 문자열 하나) 를 가지고 있고, 이것을 반응형으로 만들고자 하는 경우 </p>
    <p> 반응형이면서 변이가능한 "객체" 반환 (이 객체는 오직 value 이라는 하나의 속성만 포함) </p>
    <!--ref 가 렌더 컨텍스트 (setup() 에서 반환된 객체) 에서 속성으로 반환되고 템플릿에서 접근되면, 자동적으로 내부 값을 풀어냅니다. 즉, 템플릿에서 .value 를 추가할 필요가 없다는 것입니다.-->
    <div>
      ref count
      {{count}}
      <button @click="increment">증가</button>
    </div>

    <div>
      non ref count
      {{nonRefCount}}
      <button @click="decrement">감소</button>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue';
const count = ref(0);
const increment = () => {
  count.value++;
  console.log(count.value);
}

let nonRefCount = 0;
const decrement = () => {
  nonRefCount--;
  console.log(nonRefCount); // nonRefCount 값은 변하지만, template에 변한 값이 나타나지 않는다.
}
</script>

<style>
</style>
