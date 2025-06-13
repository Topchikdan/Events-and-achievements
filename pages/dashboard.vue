<template>
  <div class="ach-layout">
    <AppSidebar />
    <main class="ach-main">
      <div class="ach-container">
        <AchievementsHeader />
        <EventHistoryList />
        <AchievementHistoryList />
      </div>
    </main>
    <BottomNavMobile v-if="isMobile" />
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import AppSidebar from '../components/AppSidebar.vue'
import AchievementsHeader from '../components/AchievementsHeader.vue'
import EventHistoryList from '../components/EventHistoryList.vue'
import AchievementHistoryList from '../components/AchievementHistoryList.vue'
import BottomNavMobile from '../components/BottomNavMobile.vue'

const isMobile = ref(false)
const handleResize = () => {
  isMobile.value = window.innerWidth < 600
}
onMounted(() => {
  handleResize()
  window.addEventListener('resize', handleResize)
})
onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
})
</script>

<style scoped lang="scss">
@import "@/assets/styles/variables.scss";
.ach-layout {
  display: flex;
  background: $bg-main;
  min-height: 100vh;
  width: 100%;
}
.ach-main {
  flex: 1;
  padding: 40px 0;
  background: $bg-main;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  @media (max-width:900px) {
    padding: 25px 0;
  }
  @media (max-width:600px) {
    padding: 12px 0 56px 0;
  }
}
.ach-container {
  width: 100%;
  max-width: 1200px;
  padding: 0 48px;
  margin: 0 auto;
  @media (max-width: 900px) {
    padding: 0 10px;
  }
  @media (max-width:600px) {
    padding: 0 5px;
  }
}
</style>
