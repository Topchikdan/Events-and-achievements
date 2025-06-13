<template>
  <div class="dash-layout">
    <AppSidebar />
    <main class="dash-main">
      <section class="profile-side">
        <ProfileCard />
      </section>

      <section class="center-side">
        <ProjectCard />
        <CompetenciesCard />
      </section>

      <section class="news-side">
        <NewsSidebar />
      </section>
    </main>
    <BottomNavMobile v-if="isMobile" />
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import AppSidebar from '../components/AppSidebar.vue'
import ProfileCard from '../components/ProfileCard.vue'
import ProjectCard from '../components/ProjectCard.vue'
import CompetenciesCard from '../components/CompetenciesCard.vue'
import NewsSidebar from '../components/NewsSidebar.vue'
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
.dash-layout {
  display: flex;
  background: $bg-main;
  min-height: 100vh;
  width: 100%;
}
.dash-main {
  flex: 1;
  display: grid;
  grid-template-columns: 340px 2fr 340px;
  gap: 28px;
  padding: 34px 38px;
  min-height: 100vh;
  @media (max-width: 1200px) {
    grid-template-columns: 220px 1fr 180px;
    padding: 14px 4px;
    gap: 8px;
  }
  @media (max-width: 900px) {
    grid-template-columns: 1fr;
    .news-side, .profile-side { margin-bottom: 22px;}
  }
  @media (max-width: 600px) {
    padding: 10px 0 60px 0;
    grid-template-columns: 1fr;
  }
}
.profile-side {
  display: flex;
  flex-direction: column;
  gap: 18px;
  min-width: 0;
}
.center-side {
  display: flex;
  flex-direction: column;
  gap: 20px;
  min-width: 0;
}
.news-side {
  min-width: 0;
}
.prof-btn {
  background: none;
  border: 1px solid #9f86ea;
  border-radius: 10px;
  padding: 9px 12px;
  color: #dedbf9;
  font-size: 1.01rem;
  font-weight: 500;
  margin-top: 18px;
  cursor: pointer;
  transition: border .16s;
  &:hover { border-color: #be73fa; color: #be73fa; }
}
</style>
