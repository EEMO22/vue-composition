<template>
  <div>
    <p>{{ message }}</p>
    <button @click="changeMessage">change</button>
  </div>
</template>

<script>
// import { ref } from 'vue';
import { useMessage } from './hooks/useMessage'

  export default {
    setup() {

      //  타입 추론이 잘 된다 (Vue3는 코어 라이브러리가 싹 다 TypeScript)
      //  ** Composition API 의 첫 번째 강력한 장점! **

      //  구조 분해 문법
      const { message, changeMessage } = useMessage();

      //  아래의 로직은 재사용(또는 다른 곳에서 사용)을 위해 useMessage.js로 이전 후 가져와 사용
      //  ** Composition API 의 두 번째 강력한 장점! **

      // //  data
      // const message = ref('hello');

      // //  methods
      // function changeMessage() {
      //   message.value = 'hi';
      // }

      //  return해야 setup 바깥에서 사용 가능
      return { message, changeMessage }
    }
  }
</script>

<style lang="scss" scoped>

</style>