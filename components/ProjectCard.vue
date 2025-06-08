<template>
  <div class="project-card">
    <div class="project-stage">
      <span class="status">
        Проект на этапе прохождения компетенций
      </span>
      <span class="icons">
        <svg v-for="n in 3" :key="n" width="16" height="16" viewBox="0 0 16 16"><g><path d="M4.08697 7.2034L9.13708 0.34968C9.43181 -0.0503179 10.0663 0.177841 10.0388 0.673938L9.68713 7.02234C9.67125 7.30891 9.89935 7.55 10.1864 7.55H11.5774C11.9744 7.55 12.213 7.99038 11.9963 8.32297L7.26101 15.5898C6.98945 16.0066 6.34211 15.8143 6.34211 15.3169V8.5C6.34211 8.22386 6.11825 8 5.8421 8H4.4895C4.07942 8 3.84371 7.53353 4.08697 7.2034Z" fill="#ECDC49"/></g></svg>
      </span>
    </div>
    <div class="proj-title">
      Разработка дашборда на Metabase BI для компании с вахтовым методом работы
    </div>
    <div class="proj-tags">
      <span>Web-разработка</span>
      <span>Дизайн</span>
      <span>Аналитика</span>
    </div>
    <div class="proj-desc">
      Разработать сервис для удобного бронирования общих ресурсов: один фотограф на организацию, один кабинет и обмен пользователями и т.д.
      <template v-if="showMore">
        <span class="proj-desc-more">
          Здесь находится подробное описание проекта: цели, требования, результаты и примеры ожидаемых решений.
        </span>
      </template>
    </div>
    <button class="proj-more" @click="showMore = !showMore">{{ showMore ? 'Скрыть' : 'Подробнее' }}</button>
    <div class="proj-actions">
      <button class="action gray" disabled>Приступить к задаче</button>
      <button class="action violet">Получить консультацию по задаче</button>
      <button class="action text" @click.prevent>Как сменить проект</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const showMore = ref(false)
</script>

<style scoped lang="scss">
.project-card {
  background: rgba(41,33,74,0.96);
  border-radius: 16px;
  padding: 28px 24px 20px 24px;
  margin-bottom: 26px;
  min-width: 0;
  font-size: .93rem;
  box-shadow: 0 6px 38px #ab9ee233;
  transition: box-shadow .15s;
  .project-stage {
    display: flex; align-items: center; gap: 10px; margin-bottom: 18px;
    .status {
      color: #64b7fc;
      font-size: 0.91rem;
      font-weight: 400;
      border: 1.2px solid #4a98d8;
      background: rgba(100,183,252,0.08);
      border-radius: 8px;
      padding: 3px 14px 3px 14px;
      opacity: 0.77;
      letter-spacing: .02em;
      margin-bottom: 2px;
      display: inline-block;
    }
    .icons { display: flex; align-items: center; gap: 3px; }
    svg { vertical-align: middle; margin-top: 0.5px; }
  }
  .proj-title {
    color: #fff;
    font-size: 1.09rem;
    font-weight: 500;
    margin-bottom: 14px;
    line-height: 1.21;
    letter-spacing: 0.005em;
  }
  .proj-tags {
    display: flex; gap: 10px;
    margin-bottom: 14px;
    span {
      color: #b8aed4;
      font-size: 0.85rem;
      background: #2e2550;
      border-radius: 6px;
      padding: 3px 10px;
      font-weight: 400;
      letter-spacing: 0.01em;
    }
  }
  .proj-desc {
    color: #b8aed4;
    margin-bottom: 6px;
    font-size: .93rem;
    opacity: 0.99;
    font-weight: 400;
    line-height: 1.43;
    .proj-desc-more {
      display: inline;
      color: #c6b1eb;
      font-size: .91rem;
      font-weight: 400;
      margin-left: 2px;
      opacity: .93;
    }
  }
  .proj-more {
    background: none;
    color: #be73fa;
    font-size: 0.93rem;
    font-weight: 400;
    margin-bottom: 6px;
    cursor: pointer;
    border: none;
    padding: 0 2px;
    border-radius: 5px;
    transition: color .13s;
    margin-top: 2px;
    &:hover { text-decoration: underline; color: #a358f3; }
  }
  .proj-actions {
    display: flex; gap: 12px;
    margin-bottom: 0;
    margin-top: 19px;
    .action {
      border-radius: 8px;
      padding: 9px 16px;
      font-size: 0.97rem;
      font-weight: 400;
      cursor: pointer;
      border: none;
      transition: background .13s;
      &.gray {
        background: #292647;
        color: #b8aed4;
        cursor: not-allowed;
      }
      &.violet {
        background: linear-gradient(90deg,#be73fa,#6a6fff);
        color: #fff;
        border: none;
        &:hover{opacity: .87;}
      }
      &.text {
        background: none;
        color: #b8aed4;
        text-decoration: none;
        font-size: .95rem;
        padding: 0 2px;
        &:hover { color: #be73fa;}
      }
    }
  }
}
</style>
