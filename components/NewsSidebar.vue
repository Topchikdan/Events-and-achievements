<template>
  <div class="news-sidebar">
    <div class="title">Новости</div>
    <div class="news-list">
      <div v-for="news in newsArr" :key="news.id" class="news-card">
        <div class="news-title">{{ news.title }}</div>
        <div class="news-date">{{ news.date }}</div>
        <div class="news-desc" v-if="news.desc">{{ news.desc }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
const newsArr = [
  { id: 1, title: "Мы рады представить новый интерфейс на дне 1С:Карьеры в политехе", date: "1 декабря 2022", desc: "" },
  { id: 2, title: "Мы взяли в разработку компетенции по управлению БД и видео-анализа!", date: "29 ноября 2022", desc: "" },
  { id: 3, title: "На портал добавлено 42 новых проекта.", date: "26 ноября 2022", desc: "" },
  { id: 4, title: "Ты это читаешь? Подойди к Марку и скажи слово «Хакатон»", date: "12 октября 2022", desc: "" },
  { id: 5, title: "Интенсив 1С:Старт начнется уже скоро!", date: "3 октября 2022", desc: "" },
  { id: 6, title: "Добавлен новый раздел «Мои достижения»", date: "28 сентября 2022", desc: "" },
  { id: 7, title: "Открылся приём заявок на демо-проекты", date: "20 сентября 2022", desc: "" },
]
</script>

<style scoped lang="scss">
@import "@/assets/styles/variables.scss";
.news-sidebar {
  background: $bg-secondary;
  border-radius: $card-radius;
  padding: 26px 26px 16px 26px;
  .title {
    font-weight: 700;
    font-size: 1.1rem;
    color: #fff;
    margin-bottom: 16px;
  }
  .news-list {
    display: flex;
    flex-direction: column;
    gap: 14px;
    max-height: 580px;
    overflow-y: auto;
    scrollbar-width: thin;
    padding-right: 6px;
  }
  .news-card {
    padding-bottom: 10px;
    border-bottom: 1px solid #372e66;
    &:last-child { border-bottom: none; }
    .news-title {
      font-weight: 500;
      font-size: 0.92rem;
      color: #fff;
      margin-bottom: 2px;
    }
    .news-date {
      color: #b8aed4;
      font-size: 0.78rem;
      margin-bottom: 1px;
    }
    .news-desc {
      color: #b8aed4;
      font-size: 0.80rem;
    }
  }
}
</style>
