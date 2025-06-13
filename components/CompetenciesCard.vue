<template>
  <div class="competencies-card">
    <div class="competencies-label">Необходимые компетенции</div>
    <div class="competencies-about" v-if="!closeAbout">
      <div class="about-bg">
        <b>Что такое необходимые компетенции?</b>
        <span class="desc">
          Чтобы приступить к выполнению задачи, тебе нужно получить необходимые знания по направлениям, которые необходимы для реализации выбранной задачи.
        </span>
      </div>
      <button class="close" @click="closeAbout = true">&times;</button>
    </div>
    <div class="competencies-row">
      <span class="dir-label">Backend</span>
      <span class="score-badge">
        <span class="score-num">4</span>
        <!-- SVG и т.д. (оставь свои SVG здесь) -->
        <svg class="score-bracket" width="18" height="18" viewBox="0 0 8 17" fill="none">
          <!-- ... -->
        </svg>
        <svg class="score-question" width="17" height="17" viewBox="0 0 17 17" fill="none">
          <!-- ... -->
        </svg>
      </span>
    </div>
    <div class="competencies-row squares-row">
      <span class="progress-icons">
        <span v-for="n in 10" :key="n" class="prog" :class="{active: n <= 4}"></span>
      </span>
      <button class="learn-btn">Начать обучение</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const closeAbout = ref(false)
</script>

<style scoped lang="scss">
.competencies-card {
  margin-left: auto;
  margin-right: auto;
  max-width: 540px;
  width: 100%;
  padding: 22px 16px 24px 16px;
  box-sizing: border-box;
  background: transparent;
}

/* ------- АДАПТИВ ------- */
@media (max-width: 1200px) {
  .competencies-card {
    max-width: 520px;
    padding: 18px 10px 20px 10px;
  }
}
@media (max-width: 900px) {
  .competencies-card {
    max-width: 96vw;
    min-width: 0;
    padding: 4vw 2vw;
  }
  .competencies-row,
  .squares-row { 
    flex-wrap: wrap;
    gap: 8px;
    justify-content: flex-start;
  }
  .squares-row .learn-btn { 
    margin-top: 7px; 
    margin-left: 0;
    width: 100%;
  }
  .squares-row .progress-icons {
    width: 100%;
    justify-content: flex-start;
  }
}
@media (max-width: 600px) {
  .competencies-card {
    max-width: 99vw;
    padding: 2vw 1vw;
  }
  .competencies-label { font-size: 1rem; }
  .squares-row .progress-icons .prog { width: 13px; height: 13px; border-radius: 3px; }
  .squares-row .learn-btn { padding: 4px 7px; font-size: 0.81rem; }
  .competencies-row .score-badge { padding: 1.5px 7px 1.5px 4px; font-size: 0.89rem; }
}

/* ------- ОСНОВНЫЕ СТИЛИ (как было) ------- */
.competencies-label {
  font-weight: 700;
  color: #fff;
  margin-bottom: 18px;
  font-size: 1.24rem;
  letter-spacing: 0.01em;
  margin-top: 38px;
}
.competencies-about {
  position: relative;
  margin-bottom: 24px;
  .about-bg {
    background: rgba(255,255,255,0.07);
    border-radius: 12px;
    padding: 15px 22px 15px 17px;
    font-size: 1.04rem;
    b {
      color: #fff;
      font-weight: 700;
      display: block;
      margin-bottom: 3px;
      font-size: 1.07rem;
    }
    .desc {
      color: #b8aed4;
      font-weight: 400;
      margin-left: 0;
      display: block;
      margin-top: 2px;
      font-size: 0.97rem;
    }
  }
  .close {
    position: absolute;
    top: 13px; right: 14px;
    background: none;
    border: none;
    color: #b8aed4;
    font-size: 1.32rem;
    cursor: pointer;
    line-height: 1;
  }
}
.competencies-row {
  display: flex;
  align-items: center;
  gap: 13px;
  margin-top: 0;
  flex-wrap: wrap;
  .dir-label {
    color: #fff;
    font-weight: 500;
    font-size: 1.09rem;
    margin-right: 8px;
  }
  .score-badge {
    display: flex;
    align-items: center;
    gap: 3px;
    border: 2px solid #e0f1fa;
    border-radius: 36px;
    padding: 1px 14px 1px 10px;
    min-width: 56px;
    min-height: 32px;
    background: none;
    .score-num {
      color: #fff;
      font-weight: 700;
      font-size: 1.15rem;
      line-height: 1;
    }
    .score-bracket, .score-question {
      height: 18px; width: 18px;
    }
    .score-bracket { margin-left: 3px;}
  }
}
.squares-row {
  margin-top: 7px;
  gap: 15px;
  .progress-icons {
    display: flex;
    gap: 7px;
    .prog {
      width: 22px; height: 22px;
      border-radius: 6px;
      border: 1.2px solid #be73fa;
      background: none;
      opacity: .7;
      transition: border 0.12s;
      &.active {
        border: 2px solid #be73fa;
        opacity: 1;
      }
    }
  }
  .learn-btn {
    background: none;
    border: 2px solid #be73fa;
    color: #fff;
    border-radius: 8px;
    padding: 6px 17px;
    font-weight: 400;
    font-size: 0.9rem;
    cursor: pointer;
    transition: border .16s;
    margin-left: 11px;
    white-space: nowrap;
    &:hover { border-color: #fff;}
  }
}
</style>
