<template>
  <section>
    <div class="section-title" @click="showAchievements = !showAchievements">
      История достижений
      <span class="chevron" :class="{ open: showAchievements }">
        <SidebarIcons name="chevron-down" />
      </span>
    </div>
    <div v-show="showAchievements">
      <div v-for="a in achievements" :key="a.id" class="achievement-card">
        <div class="icon">
          <img src="@/assets/achievement.jpg" alt="Достижение" />
        </div>
        <div class="info">
          <div class="title">{{ a.title }}</div>
          <div class="desc">{{ a.desc }}</div>
        </div>
        <div class="date">{{ a.date }}</div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import SidebarIcons from './SidebarIcons.vue'
const showAchievements = ref(true)
const achievements = ref([
  { id: 1, date: '23 января в 18:00', title: 'Получено достижение', desc: 'Вы зарегистрировались на платформе Октагон' },
  { id: 2, date: '23 января в 18:00', title: 'Получено достижение', desc: 'Вы зарегистрировались на платформе Октагон' }
])
</script>

<style scoped lang="scss">
@import "@/assets/styles/variables.scss";
.section-title {
  color: $text-main;
  font-size: 1.1rem;
  font-weight: 600;
  margin: 18px 0 12px;
  cursor: pointer;
  display: flex;
  align-items: center;
}
.chevron {
  margin-left: 10px;
  display: inline-block;
  transition: transform 0.18s;
  &.open {
    transform: rotate(180deg);
  }
}
.achievement-card {
  background: $bg-secondary;
  border-radius: $card-radius;
  padding: 12px 14px;
  margin-bottom: 10px;
  display: flex; align-items: center;
  @media (max-width: 900px) { padding: 8px 7px; border-radius: 9px; }
  @media (max-width: 600px) { padding: 5px 3px; border-radius: 6px; }
  .icon {
    width: 34px; height: 34px;
    border-radius: 8px;
    background: #322a5b;
    margin-right: 12px;
    display: flex; align-items: center; justify-content: center;
    img {
      width: 100%; height: 100%;
      border-radius: 6px;
      object-fit: cover;
      display: block;
    }
    @media (max-width: 900px) { width: 23px; height: 23px;}
    @media (max-width: 600px) { width: 15px; height: 15px;}
  }
  .info {
    flex: 1;
    .title { font-weight: 700; margin-bottom: 2px; color: #fff; font-size: 1rem;
      @media (max-width: 900px) { font-size: .93rem; }
      @media (max-width: 600px) { font-size: .87rem; }
    }
    .desc { font-size: .81rem; color: $text-secondary; }
  }
  .date {
    color: $text-secondary; font-size: .81rem;
    white-space: nowrap; margin-left: 10px;
    @media (max-width: 900px) { font-size: .72rem;}
    @media (max-width: 600px) { font-size: .68rem;}
  }
}
</style>
