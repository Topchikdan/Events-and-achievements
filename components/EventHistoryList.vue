<template>
  <section class="event-list">
    <div class="section-title" @click="showEvents = !showEvents">
      История событий
      <span class="chevron" :class="{ open: showEvents }">
        <SidebarIcons name="chevron-down" />
      </span>
    </div>
    <div v-show="showEvents">
      <div
        class="event-card"
        v-for="(event, idx) in events"
        :key="idx"
        :class="{ last: idx === events.length - 1 }"
      >
        <div :class="['event-status', event.status]">{{ event.statusText }}</div>
        <div class="event-title">{{ event.title }}</div>
        <div class="event-date">{{ event.date }}</div>
        <template v-if="event.descShort">
          <div v-if="showDesc && idx === 0" class="event-desc" v-html="event.descFull"></div>
          <div v-else-if="idx === 0" class="event-desc-short" v-html="event.descShort"></div>
          <button v-if="idx === 0" class="event-more" @click="showDesc = !showDesc">
            {{ showDesc ? "Скрыть" : "Подробнее" }}
          </button>
        </template>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import SidebarIcons from './SidebarIcons.vue'
const showEvents = ref(true)
const showDesc = ref(false)
const events = [
  {
    status: '',
    statusText: 'ПРЕДСТОЯЩЕЕ СОБЫТИЕ',
    title: 'Интенсив Твой старт в 1С (Приморский край)',
    date: 'Даты проведения — 03.04.2025 – 16.04.2025',
    descShort:
      `<b>Интенсив «Твой старт в 1С»</b> — это уникальное мероприятие, которое пройдёт в Приморском крае и предоставит возможность участникам освоить основы работы в программе 1С. На интенсиве вы получите знания и навыки, необходимые для успешной карьеры в сфере бухгалтерии и управления бизнесом. ...`,
    descFull:
      `<b>Интенсив «Твой старт в 1С»</b> — это уникальное мероприятие, которое пройдёт в Приморском крае и предоставит возможность участникам освоить основы работы в программе 1С. На интенсиве вы получите знания и навыки, необходимые для успешной карьеры в сфере бухгалтерии и управления бизнесом.<br><br>
      Интенсив включает в себя:
      <ol>
        <li>теоретические лекции</li>
        <li>практические занятия</li>
      </ol>
      Они помогут вам разобраться в основных понятиях и принципах работы с программой 1С. Опытные преподаватели поделятся своим опытом и знаниями, а также ответят на все ваши вопросы.<br><br>
      В рамках мероприятия вы сможете пообщаться с профессионалами в области 1С, задать им интересующие вас вопросы и получить ценные советы по дальнейшему развитию в этой сфере.<br><br>
      <b>Интенсив «Твой старт в 1С»</b> — это отличный способ начать свой путь в мире бухгалтерии и управления бизнесом, используя передовые технологии и программы. Присоединяйтесь к нам и откройте новые горизонты возможностей!`
  },
  {
    status: 'current',
    statusText: 'ТЕКУЩЕЕ СОБЫТИЕ',
    title: 'Интенсив Web-разработка',
    date: 'Даты проведения — 20.03.2025 – 01.04.2025'
  },
  {
    status: 'finished',
    statusText: 'ЗАВЕРШЕНО',
    title: 'Интенсив Web-разработка',
    date: 'Даты проведения — 19.02.2025 – 20.02.2025'
  }
]
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
.event-list {
  display: flex;
  flex-direction: column;
}
.event-card {
  background: #26204c;
  border-radius: 16px;
  padding: 22px 22px 16px 22px;
  margin-bottom: 16px;
  @media (max-width: 900px) { padding: 12px 10px 10px 10px; border-radius: 12px;}
  @media (max-width: 600px) { padding: 7px 6px 7px 6px; border-radius: 8px;}
}
.event-card.last {
  margin-bottom: 0;
}
.event-status {
  font-size: 12px;
  color: #b8aed4;
  font-weight: 400;
  opacity: 0.55;
  margin-bottom: 7px;
  letter-spacing: 0.04em;
  text-transform: uppercase;
}
.event-status.current { opacity: 0.63; }
.event-status.finished { opacity: 0.4; }
.event-title {
  font-size: 17px;
  font-weight: 500;
  color: #fff;
  margin-bottom: 9px;
  @media (max-width: 900px) { font-size: 14px;}
  @media (max-width: 600px) { font-size: 13px;}
}
.event-date {
  display: inline-block;
  font-size: 12px;
  color: #fff;
  background: #3d3460;
  border-radius: 6px;
  padding: 2.5px 12px 2.5px 12px;
  margin-bottom: 13px;
  @media (max-width: 900px) { font-size: 10px; padding: 2px 8px;}
  @media (max-width: 600px) { font-size: 9px; }
}
.event-desc, .event-desc-short {
  font-size: 14px;
  color: #b8aed4;
  font-weight: 400;
  margin-top: 11px;
  margin-bottom: 7px;
  opacity: 0.8;
  line-height: 1.5;
  b { color: #fff; font-weight: 600;}
  ol { margin: 6px 0 6px 16px; padding: 0;}
  @media (max-width: 900px) { font-size: 12px; }
  @media (max-width: 600px) { font-size: 11px;}
}
.event-desc-short { margin-bottom: 0; }
.event-more {
  display: block;
  margin-top: 9px;
  background: none;
  border: none;
  color: #fff;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  padding: 0;
  text-align: left;
  transition: color 0.13s;
  &:hover { color: #be73fa; }
  @media (max-width: 900px) { font-size: 13px;}
  @media (max-width: 600px) { font-size: 11px;}
}
</style>
