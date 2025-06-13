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
        <svg class="score-bracket" width="8" height="17" viewBox="0 0 8 17" fill="none" xmlns="http://www.w3.org/2000/svg">
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
        <svg class="score-question" width="17" height="17" viewBox="0 0 17 17" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M8.47656 15.5C4.61057 15.5 1.47656 12.366 1.47656 8.5C1.47656 4.63401 4.61057 1.5 8.47656 1.5C12.3426 1.5 15.4766 4.63401 15.4766 8.5C15.4766 12.366 12.3426 15.5 8.47656 15.5ZM8.47656 16.5C12.8948 16.5 16.4766 12.9183 16.4766 8.5C16.4766 4.08172 12.8948 0.5 8.47656 0.5C4.05828 0.5 0.476562 4.08172 0.476562 8.5C0.476562 12.9183 4.05828 16.5 8.47656 16.5Z" fill="url(#paint0_linear_9759_26993)"/>
          <path d="M5.73167 6.28615C5.72408 6.42237 5.83647 6.53271 5.9729 6.53271H6.79738C6.93545 6.53271 7.04524 6.42013 7.06379 6.28331C7.15274 5.62718 7.60306 5.14893 8.40578 5.14893C9.09133 5.14893 9.71975 5.4917 9.71975 6.31689C9.71975 6.95166 9.34523 7.24365 8.7549 7.68799C8.08205 8.17676 7.54885 8.74805 7.58693 9.6748L7.5899 9.89161C7.59178 10.0283 7.70314 10.1382 7.83988 10.1382H8.6509C8.78897 10.1382 8.9009 10.0263 8.9009 9.88818V9.78271C8.9009 9.06543 9.17385 8.85596 9.91018 8.29736C10.5196 7.83398 11.1543 7.31982 11.1543 6.24072C11.1543 4.72998 9.87844 4 8.48195 4C7.21487 4 5.8262 4.59061 5.73167 6.28615ZM7.28859 12.0488C7.28859 12.582 7.71389 12.9756 8.29787 12.9756C8.90725 12.9756 9.32619 12.582 9.32619 12.0488C9.32619 11.4966 8.90725 11.1094 8.29787 11.1094C7.71389 11.1094 7.28859 11.4966 7.28859 12.0488Z" fill="url(#paint1_linear_9759_26993)"/>
          <defs>
          <linearGradient id="paint0_linear_9759_26993" x1="0.814116" y1="0.49998" x2="16.4795" y2="0.749064" gradientUnits="userSpaceOnUse">
          <stop stop-color="#1E768E"/>
          <stop offset="1" stop-color="#9652D4"/>
          </linearGradient>
          <linearGradient id="paint1_linear_9759_26993" x1="0.814116" y1="0.49998" x2="16.4795" y2="0.749064" gradientUnits="userSpaceOnUse">
          <stop stop-color="#1E768E"/>
          <stop offset="1" stop-color="#9652D4"/>
          </linearGradient>
          </defs>
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
