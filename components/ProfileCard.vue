<template>
  <div class="profile-card">
    <div class="profile-title-row">
      <span class="profile-title">Профиль</span>
      <button class="coins-btn">
        <svg width="16" height="16" viewBox="0 0 8 17" fill="none" style="margin-right:4px;">
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
        <span class="octo">окто</span><span class="coins">коинов</span>
      </button>
    </div>

    <div class="profile-avatar-row">
      <div class="big-avatar"><span>K</span></div>
    </div>

    <div class="fio-block">
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

    <div class="achievements-block">
      <div class="ach-title">Мои достижения</div>
      <div class="ach-row">
        <img class="ach-img" src="../assets/achievement.jpg" alt="ach" />
        <div class="ach-empty"></div>
        <div class="ach-empty"></div>
        <div class="ach-empty"></div>
        <div class="ach-empty"></div>
        <div class="ach-empty"></div>
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
  padding: 22px 14px 20px 14px;
  display: flex;
  flex-direction: column;
  min-width: 0;
  box-sizing: border-box;

  .profile-title-row {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 14px;
    .profile-title {
      color: #fff;
      font-size: 1.25rem;
      font-weight: 700;
      letter-spacing: 0.01em;
    }
    .coins-btn {
      display: flex;
      align-items: center;
      background: none;
      border: 1.2px solid #e0f1fa;
      border-radius: 11px;
      padding: 2px 11px 2px 7px;
      font-size: 0.90rem;
      color: #fff;
      font-weight: 400;
      .coins-value { color: #fff; font-size: 0.93rem; font-weight: 600; margin-right: 2px;}
      .octo {
        font-weight: 600;
        background: linear-gradient(90deg,#be73fa 40%,#6ec8f2 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        margin-left: 3px;
        margin-right: 0;
        font-size: 0.90rem;
      }
      .coins {
        color: #c9b9ed;
        margin-left: 1px;
        font-weight: 400;
        font-size: 0.86rem;
      }
    }
  }

  .profile-avatar-row {
    display: flex;
    justify-content: center;
    margin-bottom: 11px;
    .big-avatar {
      width: 92%;
      aspect-ratio: 1 / 1;
      max-width: 140px;
      min-width: 75px;
      background: transparent;
      border-radius: 50%;
      border: 2.7px solid #a586f8;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 2px auto;
      color: #fff;
      font-size: 2.8rem;
      font-weight: 800;
      letter-spacing: 0.04em;
      box-sizing: border-box;
      transition: 0.2s;
    }
  }

  .fio-block {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 12px;
    .fio {
      color: #fff;
      font-size: 1.34rem;
      font-weight: 700;
      line-height: 1.14;
      margin-bottom: 11px;
      text-align: center;
      margin-top: 1px;
    }
    .levels-labels {
      width: 100%;
      display: flex; justify-content: space-between;
      margin-bottom: 0px;
      margin-top: 0;
      .level-active-label {
        color: #7bfca9;
        font-size: 1.04rem;
        font-weight: 700;
      }
      .level-next-label {
        color: #b8aed4;
        font-size: 1.01rem;
        font-weight: 600;
        opacity: 0.32;
      }
    }
    .level-row {
      width: 100%;
      margin: 0 auto 0 auto;
      display: flex;
      align-items: center;
      .level-bar {
        height: 9px;
        width: 97%;
        max-width: 200px;
        background: #40397a;
        border-radius: 5px;
        margin: 0 auto;
        margin-top: 5px;
        position: relative;
        overflow: hidden;
        .level-bar-fill {
          background: linear-gradient(90deg,#7bfca9 80%,#40397a 100%);
          height: 100%;
          width: 47%;
          border-radius: 4px;
          position: absolute;
          left: 0; top: 0;
        }
      }
    }
  }

  .achievements-block {
    margin-bottom: 13px;
    .ach-title {
      color: #fff;
      font-size: 0.94rem;
      font-weight: 600;
      margin-bottom: 7px;
      margin-top: 2px;
      text-align: center;
    }
    .ach-row {
      display: flex;
      gap: 6px;
      justify-content: center;
      margin-bottom: 8px;
      .ach-img {
        width: 26px;
        height: 26px;
        border-radius: 6px;
        object-fit: cover;
        border: 1px solid #6641b3;
      }
      .ach-empty {
        width: 26px;
        height: 26px;
        background: rgba(131,96,204,0.13);
        border-radius: 6px;
        border: 1px solid #3d3165;
      }
    }
  }

  .prof-btn {
    background: none;
    border: 1.1px solid #be73fa;
    border-radius: 5px;
    color: #dedbf9;
    font-size: 0.90rem;
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
    padding: 23px 16px 14px 16px;
    min-width: 0;
    box-shadow: 0 2px 30px #5741e81a;
    .event-label {
      color: #a099bc;
      font-size: 0.82rem;
      letter-spacing: 0.03em;
      font-weight: 500;
      margin-bottom: 10px;
      text-transform: uppercase;
    }
    .event-title {
      color: #fff;
      font-size: 1.19rem;
      font-weight: 700;
      margin-bottom: 13px;
      line-height: 1.14;
    }
    .event-date {
      .event-date-label {
        display: inline-block;
        background: rgba(62, 72, 142, 0.52);
        color: #fff;
        font-size: 0.92rem;
        font-weight: 600;
        border-radius: 9px;
        padding: 7px 14px 7px 14px;
        margin-bottom: 14px;
      }
      margin-bottom: 18px;
    }
    .event-desc {
      margin-top: 6px;
      color: #b8aed4;
      font-size: 0.98rem;
      line-height: 1.47;
      .event-desc-title {
        color: #b8aed4;
        font-size: 0.96rem;
        font-weight: 400;
        margin-bottom: 17px;
      }
      .event-desc-title b {
        color: #fff;
        font-size: 1.03rem;
        font-weight: 700;
      }
      .event-desc-sub {
        margin-bottom: 10px;
        .desc-list-title {
          color: #b8aed4;
          font-weight: 400;
          font-size: 0.98rem;
          margin-bottom: 2px;
          margin-top: 5px;
        }
        .desc-list {
          margin: 0 0 6px 18px;
          color: #b8aed4;
          font-size: 0.98rem;
          font-weight: 400;
        }
        .desc-bottom {
          margin-left: 10px;
          color: #b8aed4;
          font-size: 0.98rem;
          margin-bottom: 4px;
          margin-top: 3px;
        }
      }
      .event-more-btn {
        color: #fff;
        font-size: 0.99rem;
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

@media (max-width: 600px) {
  .profile-card {
    padding: 4vw 0.5vw;
    .profile-title-row .profile-title { font-size: 0.91rem;}
    .profile-avatar-row .big-avatar { font-size: 1.2rem;}
    .fio-block .fio { font-size: .72rem;}
    .fio-block .levels-labels .level-active-label { font-size: .66rem;}
    .fio-block .levels-labels .level-next-label { font-size: .65rem;}
    .fio-block .level-row .level-bar { height: 5px; }
    .achievements-block .ach-title { font-size: .63rem; }
    .achievements-block .ach-row .ach-img, .achievements-block .ach-row .ach-empty { width: 14px; height: 14px;}
    .prof-btn { font-size: 0.66rem; }
    .event-card { padding: 10px 3px 8px 3px;
      .event-title { font-size: .71rem; }
      .event-label { font-size: .39rem; }
      .event-date .event-date-label { font-size: .52rem;}
      .event-desc-title, .event-desc-sub, .desc-list, .desc-bottom, .event-more-btn { font-size: .55rem;}
    }
  }
}
</style>
