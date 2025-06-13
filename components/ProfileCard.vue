<template>
  <div class="profile-card">
    <div class="profile-title-row">
      <span class="profile-title">Профиль</span>
      <button class="coins-btn">
        <svg width="14" height="14" viewBox="0 0 8 17" fill="none" style="margin-right:4px;">
          <mask id="mask0_9780_46309" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="0" y="0" width="8" height="17">
            <path d="M1.72368 6.07749L0.523438 8.89404L1.72368 11.7106L2.86658 14.5509L5.70689 15.6938L7.74542 16.5625V14.3624L6.44359 13.8076L4.42295 12.9945L3.60987 10.9739L2.756 8.97015L3.60987 6.96641L4.42295 4.94577L6.44359 4.1327L7.74542 3.57793L7.74543 0.432865L6.46201 1.7725L5.70689 2.09429L2.86658 3.23719L1.72368 6.07749Z" fill="#D9D9D9"/>
          </mask>
          <g mask="url(#mask0_9780_46309)">
            <path d="M-0.339844 18.7891L-0.339844 -0.238424H8.52274L8.52274 18.7891H-0.339844Z" fill="#1E768E"/>
            <path d="M-0.339844 18.4336L-0.339844 -0.593893H8.52274L8.52274 18.4336H-0.339844Z" fill="white"/>
          </g>
          <mask id="mask1_9780_46309" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="4" y="4" width="4" height="9">
            <path d="M5.10128 7.51466L4.52344 8.87064L5.10128 10.2266L5.65151 11.594L7.01893 12.1443L8.00035 12.5625V11.5033L7.3736 11.2362L6.40079 10.8448L6.00935 9.87195L5.59827 8.90729L6.00935 7.94262L6.40079 6.96981L7.3736 6.57837L8.00035 6.31129L8.00035 4.79715L7.38247 5.44209L7.01893 5.59701L5.65151 6.14724L5.10128 7.51466Z" fill="#D9D9D9"/>
          </mask>
          <g mask="url(#mask1_9780_46309)">
            <path d="M4.10938 13.6328L4.10938 4.47234H8.37612L8.37612 13.6328H4.10938Z" fill="#9353D2"/>
            <path d="M4.10938 13.6328L4.10938 4.47234H8.37612L8.37612 13.6328H4.10938Z" fill="white"/>
          </g>
        </svg>
        <span class="coins-value">0</span>
        <span class="octo">окто</span>
        <span class="coins">коинов</span>
      </button>
    </div>

    <div class="profile-info">
      <div class="big-avatar"><span>K</span></div>
      <div class="fio-levels">
        <div class="fio">Константинов<br />Константин</div>
        <div class="levels-labels">
          <span class="level-active-label">1 уровень</span>
          <span class="level-next-label">2 уровень</span>
        </div>
        <div class="level-row">
          <div class="level-bar">
            <div class="level-bar-fill"></div>
          </div>
        </div>
      </div>
    </div>

    <div class="achievements-block">
      <div class="ach-title">Мои достижения</div>
      <div class="ach-row">
        <img class="ach-img" src="../assets/achievement.jpg" alt="ach" />
        <div class="ach-empty"></div>
        <div class="ach-empty"></div>
        <div class="ach-empty"></div>
        <div class="ach-empty"></div>
        <div class="ach-empty"></div>
        <div class="ach-img ach-svg">
          <svg width="16" height="11" viewBox="0 0 16 11" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M1 5.5C1 5.22386 1.22386 5 1.5 5L13.2929 5L10.1464 1.85355C9.95118 1.65829 9.95118 1.34171 10.1464 1.14645C10.3417 0.951183 10.6583 0.951183 10.8536 1.14645L14.8536 5.14645C15.0488 5.34171 15.0488 5.65829 14.8536 5.85355L10.8536 9.85355C10.6583 10.0488 10.3417 10.0488 10.1464 9.85355C9.95118 9.65829 9.95118 9.34171 10.1464 9.14645L13.2929 6L1.5 6C1.22386 6 1 5.77614 1 5.5Z" fill="white" stroke="white" stroke-width="0.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
      </div>
    </div>

    <button class="prof-btn">Результаты профориентации</button>

    <div class="event-card">
      <div class="event-label">ТЕКУЩЕЕ СОБЫТИЕ</div>
      <div class="event-title">
        Интенсив Твой старт в 1С <br>
        (Приморский край)
      </div>
      <div class="event-date">
        <span class="event-date-label">
          Даты проведения — 27.03.2025 – 03.04.2025
        </span>
      </div>
      <div class="event-desc">
        <div class="event-desc-title">
          <b>Интенсив «Твой старт в 1C»</b> — это уникальное мероприятие, которое пройдет в Приморском крае и предоставит возможность участникам освоить основы работы в программе 1C.
          <br><br>
          На интенсиве вы получите знания и навыки, необходимые для успешной карьеры в сфере бухгалтерии и управления бизнесом.
        </div>
        <div class="event-desc-sub" v-if="showMore">
          <div class="desc-list-title">Интенсив включает в себя:</div>
          <ol class="desc-list">
            <li>теоретические лекции</li>
            <li>практические занятия</li>
          </ol>
          <div class="desc-bottom">
            Они помогут вам разобраться в основных понятиях и принципах работы с программой 1C. Опытные преподаватели поделятся своим опытом и знаниями, а также ответят на...
          </div>
        </div>
        <button class="event-more-btn" @click="showMore = !showMore">
          {{ showMore ? "Скрыть" : "Подробнее" }}
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const showMore = ref(false)
</script>

<style scoped lang="scss">
.profile-card {
  background: #262153;
  border-radius: 32px;
  padding: clamp(14px, 2vw, 38px) clamp(2vw, 3vw, 38px) clamp(12px, 2vw, 28px) clamp(2vw, 3vw, 38px);
  display: flex;
  flex-direction: column;
  max-width: 530px;
  margin: 0 auto;
  min-width: 0;
  box-sizing: border-box;

  .profile-title-row {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: clamp(9px, 2vw, 18px);
    .profile-title {
      color: #fff;
      font-size: clamp(1rem, 2vw, 1.32rem);
      font-weight: 600;
      letter-spacing: 0.01em;
    }
    .coins-btn {
      display: flex;
      align-items: center;
      background: none;
      border: 1px solid #e0f1fa;
      border-radius: 11px;
      padding: 2px clamp(7px, 2vw, 13px);
      font-size: clamp(0.82rem, 1.6vw, 0.95rem);
      color: #fff;
      font-weight: 400;
      .coins-value { color: #fff; font-size: inherit; font-weight: 500; margin-right: 1.5px;}
      .octo {
        font-weight: 500;
        background: linear-gradient(90deg,#be73fa 40%,#6ec8f2 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        margin-left: 2.5px;
        margin-right: 0;
        font-size: inherit;
      }
      .coins {
        color: #c9b9ed;
        margin-left: 1px;
        font-weight: 400;
        font-size: inherit;
      }
    }
  }

  .profile-info {
    display: flex;
    align-items: center;
    gap: clamp(9px, 2vw, 22px);
    margin-bottom: clamp(11px, 2vw, 24px);
    .big-avatar {
      width: clamp(35px, 12vw, 68px);
      height: clamp(35px, 12vw, 68px);
      min-width: clamp(35px, 12vw, 68px);
      min-height: clamp(35px, 12vw, 68px);
      background: transparent;
      border-radius: 50%;
      border: 2px solid #a586f8;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      font-size: clamp(0.95rem, 2.5vw, 1.39rem);
      font-weight: 600;
      margin-right: 2px;
    }
    .fio-levels {
      display: flex;
      flex-direction: column;
      justify-content: center;
      flex: 1;
      min-width: 0;
      .fio {
        color: #fff;
        font-size: clamp(0.79rem, 2vw, 1.14rem);
        font-weight: 400;
        line-height: 1.14;
        margin-bottom: 7px;
        text-align: left;
        margin-top: 0;
        overflow-wrap: anywhere;
      }
      .levels-labels {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 3px;
        .level-active-label {
          color: #7bfca9;
          font-size: clamp(0.71rem, 1.3vw, 0.99rem);
          font-weight: 500;
        }
        .level-next-label {
          color: #b8aed4;
          font-size: clamp(0.71rem, 1.3vw, 0.99rem);
          font-weight: 400;
          opacity: 0.32;
          margin-left: auto;
        }
      }
      .level-row {
        width: 100%;
        margin: 0;
        display: flex;
        align-items: center;
        .level-bar {
          height: clamp(5px, 1vw, 9px);
          width: 100%;
          max-width: 325px;
          background: #40397a;
          border-radius: 4px;
          position: relative;
          overflow: hidden;
          margin-top: 2px;
          .level-bar-fill {
            background: linear-gradient(90deg,#7bfca9 80%,#40397a 100%);
            height: 100%;
            width: 9%;
            border-radius: 4px;
            position: absolute;
            left: 0; top: 0;
            transition: width .22s;
          }
        }
      }
    }
  }

  .achievements-block {
    margin-bottom: clamp(11px, 2vw, 20px);
    .ach-title {
      color: #fff;
      font-size: clamp(1rem, 2vw, 1.2rem);
      font-weight: 650;
      margin-bottom: clamp(7px, 1.5vw, 14px);
      text-align: left;
    }
    .ach-row {
      display: grid;
      grid-template-columns: repeat(7, 1fr);
      gap: clamp(4px, 1.5vw, 10px);
      width: 100%;
      margin-bottom: clamp(7px, 1.5vw, 15px);
      .ach-img,
      .ach-empty,
      .ach-svg {
        width: 100%;
        aspect-ratio: 1 / 1;
        border-radius: 8px;
        background: rgba(131,96,204,0.13);
        border: 1.5px solid #3d3165;
        display: flex;
        align-items: center;
        justify-content: center;
        object-fit: cover;
        overflow: hidden;
        min-width: 0;
      }
      .ach-img {
        background: #262153;
        border: 1.5px solid #6641b3;
        object-fit: cover;
        padding: 0;
      }
    }
  }

  .prof-btn {
    background: none;
    border: 1.1px solid #be73fa;
    border-radius: 5px;
    color: #dedbf9;
    font-size: clamp(0.82rem, 1.6vw, 1rem);
    font-weight: 500;
    margin-bottom: 16px;
    cursor: pointer;
    width: 100%;
    padding: 7px 4px;
    transition: border .16s, color .16s;
    text-align: center;
    &:hover { border-color: #be73fa; color: #be73fa; }
  }

  .event-card {
    margin-top: 7px;
    background: #2c2554;
    border-radius: 19px;
    padding: clamp(13px, 2vw, 25px) clamp(7px, 2vw, 18px) clamp(8px, 2vw, 19px) clamp(7px, 2vw, 18px);
    min-width: 0;
    box-shadow: 0 2px 30px #5741e81a;
    .event-label {
      color: #a099bc;
      font-size: clamp(0.67rem, 1vw, 0.9rem);
      letter-spacing: 0.03em;
      font-weight: 500;
      margin-bottom: 10px;
      text-transform: uppercase;
    }
    .event-title {
      color: #fff;
      font-size: clamp(0.93rem, 2vw, 1.23rem);
      font-weight: 500;
      margin-bottom: 13px;
      line-height: 1.14;
    }
    .event-date {
      .event-date-label {
        display: inline-block;
        background: rgba(62, 72, 142, 0.52);
        color: #fff;
        font-size: clamp(0.72rem, 1vw, 1.01rem);
        font-weight: 400;
        border-radius: 9px;
        padding: 6px 13px;
        margin-bottom: 14px;
      }
      margin-bottom: 18px;
    }
    .event-desc {
      margin-top: 6px;
      color: #b8aed4;
      font-size: clamp(0.85rem, 2vw, 1.04rem);
      line-height: 1.47;
      .event-desc-title {
        color: #b8aed4;
        font-size: inherit;
        font-weight: 400;
        margin-bottom: 17px;
      }
      .event-desc-title b {
        color: #fff;
        font-size: inherit;
        font-weight: 700;
      }
      .event-desc-sub {
        margin-bottom: 10px;
        .desc-list-title {
          color: #b8aed4;
          font-weight: 400;
          font-size: inherit;
          margin-bottom: 2px;
          margin-top: 5px;
        }
        .desc-list {
          margin: 0 0 6px 18px;
          color: #b8aed4;
          font-size: inherit;
          font-weight: 400;
        }
        .desc-bottom {
          margin-left: 10px;
          color: #b8aed4;
          font-size: inherit;
          margin-bottom: 4px;
          margin-top: 3px;
        }
      }
      .event-more-btn {
        color: #fff;
        font-size: clamp(0.81rem, 1.2vw, 1.04rem);
        margin-top: 4px;
        text-decoration: underline;
        transition: color .13s;
        background: none;
        border: none;
        cursor: pointer;
        padding: 0;
        &:hover { color: #be73fa; }
      }
    }
  }
}

@media (max-width: 400px) {
  .profile-card {
    .profile-title-row .profile-title { font-size: 0.78rem;}
    .profile-info .big-avatar { width: 24px; height: 24px; font-size: 0.71rem;}
    .profile-info .fio-levels .fio { font-size: .57rem;}
    .profile-info .levels-labels .level-active-label,
    .profile-info .levels-labels .level-next-label { font-size: .49rem;}
    .profile-info .level-row .level-bar { height: 3.5px;}
    .achievements-block .ach-title { font-size: .69rem; }
    .achievements-block .ach-row .ach-img, .achievements-block .ach-row .ach-empty, .achievements-block .ach-row .ach-svg { border-radius: 5px;}
    .prof-btn { font-size: 0.52rem; }
  }
}
</style>
