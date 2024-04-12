<template>
  <div class="Person">
    姓：<input type="text" v-model="firstName" /><br />
    名：<input type="text" v-model="lastName" /><br />
    全名：<span>{{ fullName }}</span
    ><br />
    <button @click="changeName">将全名改为li-si</button>
  </div>
</template>
<script lang="ts" setup>
import { computed, ref } from 'vue'

let firstName = ref('张')
let lastName = ref('三')

// // only read
// let fullName = computed(() => {
//   return firstName.value.slice(0, 1).toUpperCase() + firstName.value.slice(1) + '-' + lastName.value
// })

// read and write
let fullName = computed({
  get() {
    return (
      firstName.value.slice(0, 1).toUpperCase() + firstName.value.slice(1) + '-' + lastName.value
    )
  },
  set(val) {
    const [str1, str2] = val.split('-')
    firstName.value = str1
    lastName.value = str2
  }
})

function changeName() {
  fullName.value = 'li-si'
}
</script>

<style scoped>
.Person {
  background-color: #99c9db;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
</style>
