<template>
  <div class="person">
    <h2>姓名:{{ Name }}</h2>
    <h2>年龄:{{ Age }}</h2>
    <button @click="changeName">修改姓名</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">显示联系方式</button>
  </div>
</template>
<script lang="ts">
export default {
  name: 'MyPerson'
}
</script>

<script lang="ts" setup>
let Name = '张三'
let Age = 18
let Tel = '135645645654'

function changeName() {
  Name = 'zhang-san'
}

function changeAge() {
  Age += 1
}
function showTel() {
  alert(Tel)
}
</script>

<style scoped>
.person {
  background-color: #bbb;
  box-shadow: 0 0 10px;
  border-radius: 20px;
  padding: 20px;
}
</style>
