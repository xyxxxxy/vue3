<template>
  <div class="Person">
    <h1>姓名：{{ person.name }}</h1>
    <h1>年龄：{{ person.age }}</h1>
    <button @click="changeName">修改姓名</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="changePerson">修改整个人</button>
  </div>
</template>
<script lang="ts" setup>
import { reactive, watch } from 'vue'

let person = reactive({
  name: '张三',
  age: 18
})

function changeName() {
  person.name += '~'
}
function changeAge() {
  person.age += 1
}
function changePerson() {
  Object.assign(person, { name: '李四', age: 33 })
}
watch(person, (newValue, oldValue) => {
  console.log('person改变了!', newValue, oldValue)
})
</script>

<style scoped>
.Person {
  background-color: #99c9db;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
</style>
