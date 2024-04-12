<template>
  <div class="Person">
    <h1>姓名：{{ person.name }}</h1>
    <h1>年龄：{{ person.age }}</h1>

    <h1>车：{{ person.car.c1 }}----{{ person.car.c2 }}</h1>
    <button @click="changeName">修改姓名</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="changeC1">修改第一辆车</button>
    <button @click="changeC2">修改第二辆车</button>
    <button @click="changeCar">修改所有车</button>
  </div>
</template>
<script lang="ts" setup>
import { reactive, watch } from 'vue'

let person = reactive({
  name: '张三',
  age: 18,
  car: {
    c1: '奔驰',
    c2: '宝马'
  }
})

function changeName() {
  person.name += '~'
}
function changeAge() {
  person.age += 1
}
function changeC1() {
  person.car.c1 = '奥迪'
}
function changeC2() {
  person.car.c2 = '大众'
}
function changeCar() {
  person.car = { c1: '雅迪', c2: '爱玛' }
}

// 对象中的变量
watch(
  () => person.name,
  (newValue, oldValue) => {
    console.log('person变化了', newValue, oldValue)
  }
)
//对象中的对象
watch(
  () => person.car,
  (newValue, oldValue) => {
    console.log('Car变化了', newValue, oldValue)
  },
  { deep: true }
)
//监视多个数据
watch([() => person.name, () => person.car.c1], (newValue, oldValue) => {
  console.log('name或者第一辆车变化了', newValue, oldValue)
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
