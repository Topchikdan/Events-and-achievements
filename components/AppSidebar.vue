<template>
  <aside class="sidebar">
    <ul>
      <li :class="{active: $route.path==='/' }">
        <NuxtLink to="/"><SidebarIcons name="home" /></NuxtLink>
      </li>
      <li :class="{active: $route.path==='/dashboard'}">
        <NuxtLink to="/dashboard"><SidebarIcons name="cup" /></NuxtLink>
      </li>
      <li :class="{active: $route.path==='/noevent'}">
        <NuxtLink to="/noevent"><SidebarIcons name="graduation" /></NuxtLink>
      </li>
      <li :class="{active: $route.path==='/events'}">
        <NuxtLink to="/events"><SidebarIcons name="book" /></NuxtLink>
      </li>
      <li :class="{active: $route.path==='/cart'}">
        <NuxtLink to="/cart"><SidebarIcons name="cart" /></NuxtLink>
      </li>
      <li :class="{active: $route.path==='/backpack'}">
        <NuxtLink to="/backpack"><SidebarIcons name="backpack" /></NuxtLink>
      </li>
      <li :class="{active: $route.path==='/favorites'}">
        <NuxtLink to="/favorites"><SidebarIcons name="heart" /></NuxtLink>
      </li>
      <li :class="{active: $route.path==='/settings'}">
        <NuxtLink to="/settings">
          <span class="icon-dot-wrap">
            <SidebarIcons name="settings" />
            <span class="dot"></span>
          </span>
        </NuxtLink>
      </li>
      <li :class="{active: $route.path==='/help'}" style="margin-top:auto;">
        <NuxtLink to="/help"><SidebarIcons name="help" /></NuxtLink>
      </li>
      <li>
        <NuxtLink to="/exit"><SidebarIcons name="exit" /></NuxtLink>
      </li>
    </ul>
  </aside>
</template>

<script setup>
import { useRoute } from 'vue-router'
import SidebarIcons from './SidebarIcons.vue'
const $route = useRoute()
</script>

<style scoped lang="scss">
@import "@/assets/styles/variables.scss";
.sidebar {
  width: 66px;
  background: $bg-secondary;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 18px 0;
  ul {
    list-style: none;
    padding: 0;
    margin: 0;
    height: 100%;
    display: flex;
    flex-direction: column;
    gap: 28px;
  }
  li {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    &.active svg {
      filter: drop-shadow(0 0 8px #be73fa);
    }
    .icon-dot-wrap {
      position: relative;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 36px; // ширина иконки + немного места для точки
      height: 36px;
    }
    .dot {
      position: absolute;
      top: 0px;
      right: 0px;
      width: 11px;
      height: 11px;
      border-radius: 50%;
      background: #be73fa;
      border: 2px solid $bg-secondary;
      box-shadow: 0 1px 3px #0002;
      display: inline-block;
      z-index: 2;
      pointer-events: none;
    }
  }
  a {
    display: flex;
    align-items: center;
    color: inherit;
    text-decoration: none;
  }
}
@media (max-width: 600px) {
  .sidebar { display: none; }
}
</style>
