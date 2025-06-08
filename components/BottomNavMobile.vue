<template>
  <nav class="bottom-nav">
    <ul>
      <li>
        <NuxtLink to="/achievements">
          <span class="icon-wrap">
            <SidebarIcons name="cup" />
          </span>
        </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/events">
          <span class="icon-wrap">
            <SidebarIcons name="book" />
            <span class="dot"></span>
          </span>
        </NuxtLink>
      </li>
      <li :class="{active: $route.path==='/' }">
        <NuxtLink to="/">
          <span class="icon-wrap">
            <SidebarIcons name="home" />
          </span>
        </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/favorites">
          <span class="icon-wrap">
            <SidebarIcons name="heart" />
          </span>
        </NuxtLink>
      </li>
      <li>
        <button class="burger-btn" @click="showMenu = true" aria-label="Меню">
          <span class="icon-wrap">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <rect y="4" width="24" height="2" rx="1" fill="#C9B9ED"/>
              <rect y="11" width="24" height="2" rx="1" fill="#C9B9ED"/>
              <rect y="18" width="24" height="2" rx="1" fill="#C9B9ED"/>
            </svg>
            <span class="dot"></span>
          </span>
        </button>
      </li>
    </ul>
    <transition name="fade">
      <div class="drawer-bg" v-if="showMenu" @click.self="showMenu = false">
        <div class="drawer">
          <button class="close-btn" @click="showMenu = false">&times;</button>
          <ul>
            <li>
              <NuxtLink to="/graduation" @click="showMenu = false">
                <SidebarIcons name="graduation" /> <span>Учёба</span>
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/backpack" @click="showMenu = false">
                <SidebarIcons name="backpack" /> <span>Рюкзак</span>
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/lock" @click="showMenu = false">
                <SidebarIcons name="lock" /> <span>Доступ</span>
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/help" @click="showMenu = false">
                <SidebarIcons name="help" /> <span>Помощь</span>
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/exit" @click="showMenu = false">
                <SidebarIcons name="exit" /> <span>Выйти</span>
              </NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import SidebarIcons from './SidebarIcons.vue'

const showMenu = ref(false)
</script>

<style scoped lang="scss">
@import "@/assets/styles/variables.scss";
.bottom-nav {
  position: fixed;
  left: 0; right: 0; bottom: 0;
  background: $bg-secondary;
  height: 58px;
  z-index: 100;
  box-shadow: 0 -4px 28px #0001;
  border-radius: 0 0 24px 24px;

  ul {
    display: flex;
    align-items: center;
    justify-content: space-around;
    height: 100%;
    margin: 0; padding: 0;
    list-style: none;
  }
  li {
    color: #b097ed;
    font-size: 24px;
    display: flex;
    align-items: center;
    justify-content: center;
    &.active svg {
      filter: drop-shadow(0 0 8px #be73fa);
    }
  }
  a, .burger-btn {
    color: inherit; text-decoration: none; display: flex; align-items: center;
    background: none; border: none; cursor: pointer; padding: 0; margin: 0;
  }
  .burger-btn {
    position: relative;
  }
}

.icon-wrap {
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
}

.dot {
  position: absolute;
  top: 3px;
  right: 6px;
  width: 11px;
  height: 11px;
  border-radius: 50%;
  background: linear-gradient(135deg,#be73fa,#6ec8f2 95%);
  border: 2px solid $bg-secondary;
  box-shadow: 0 1px 3px #0002;
  content: "";
  display: inline-block;
  z-index: 1;
}

.drawer-bg {
  position: fixed; inset: 0;
  background: rgba(30,20,65,0.76);
  z-index: 200;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
}
.drawer {
  width: 100vw;
  max-width: 320px;
  background: $bg-secondary;
  min-height: 280px;
  padding: 24px 14px 32px 24px;
  border-radius: 20px 0 0 0;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  animation: slideIn .2s cubic-bezier(.4,0,.2,1);
  ul {
    margin: 28px 0 0 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 22px;
    list-style: none;
    width: 100%;
    li {
      display: flex;
      align-items: center;
      width: 100%;
      a {
        display: flex; align-items: center; gap: 16px;
        color: #c9b9ed; text-decoration: none;
        font-size: 18px; font-weight: 500;
        width: 100%;
      }
    }
  }
  .close-btn {
    font-size: 32px;
    background: none;
    border: none;
    color: #bdb4ef;
    align-self: flex-end;
    cursor: pointer;
    margin-bottom: 8px;
    line-height: 1;
  }
}
.fade-enter-active, .fade-leave-active {
  transition: opacity .16s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
@keyframes slideIn {
  from { transform: translateY(100%);}
  to { transform: translateY(0);}
}
@media (min-width: 600px) {
  .bottom-nav { display: none; }
}
</style>
