<template>
  <div class="person">???</div>
</template>
<script lang="ts" setup name="Person">
import { type PersonInter } from '@/types'

let personList: Array<PersonInter> = [
  { id: '01', name: 'ww', age: 10 },
  { id: '02', name: 'ee', age: 55 },
  { id: '03', name: 'qq', age: 5 }
]
</script>

<style scoped>
.person {
  background-color: #99c9db;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
</style>
