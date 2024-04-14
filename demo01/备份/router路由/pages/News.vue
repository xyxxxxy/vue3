<template>
  <div class="news">
    <ul>
      <li v-for="news in newList" :key="news.id">
        <RouterLink
          :to="{
            name: 'xiang',
            query: {
              id: news.id,
              title: news.title,
              content: news.content
            }
          }"
        >
          {{ news.title }}
        </RouterLink>
      </li>
    </ul>
    <div class="news-content">
      <router-view></router-view>
    </div>
  </div>
</template>

<script setup lang="ts" name="News">
import { reactive } from 'vue'
import Detail from './Detail.vue'
const newList = reactive([
  { id: 'asdasd01', title: '新闻1', content: '西蓝花' },
  { id: 'asdasd02', title: '新闻2', content: '学IT' },
  { id: 'asdasd03', title: '新闻3', content: '明天是周一' },
  { id: 'asdasd04', title: '新闻4', content: '快过年了' }
])
</script>

<style scoped>
/* 新闻 */
.news {
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  height: 100%;
}
.news ul {
  margin-top: 30px;
  list-style: none;
  padding-left: 10px;
}
.news li > a {
  font-size: 18px;
  line-height: 40px;
  text-decoration: none;
  color: #64967e;
  text-shadow: 0 0 1px rgb(0, 84, 0);
}
.news-content {
  width: 70%;
  height: 90%;
  border: 1px solid;
  margin-top: 20px;
  border-radius: 10px;
}
</style>
