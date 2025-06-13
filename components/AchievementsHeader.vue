<template>
  <div class="header-row">
    <div class="ach-card achievements">
      <div class="ach-label">Мои достижения</div>
      <div class="achievements-list">
        <div class="ach-item active">
          <img src="@/assets/achievement.jpg" alt="Достижение" />
        </div>
        <div class="ach-item"></div>
        <div class="ach-item"></div>
        <div class="ach-item"></div>
        <div class="ach-item"></div>
        <div class="ach-item"></div>
      </div>
    </div>
    <div class="ach-card exp">
      <div class="ach-label">Мой опыт</div>
      <div class="ach-value">
        <span class="main-num">250</span>
        <span class="main-num">из 1000</span>
      </div>
    </div>
    <div class="ach-card balance">
      <div class="ach-label">Мой баланс</div>
      <div class="ach-value">
        <span class="main-num">10</span>
        <span class="octo-gradient">окто</span>
        <span class="octo-gradient main-sub">коинов</span>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import "@/assets/styles/variables.scss";

.header-row {
  display: flex;
  gap: 18px;
  margin-bottom: 28px;
  flex-wrap: wrap;
  @media (max-width: 900px) {
    flex-direction: column;
    gap: 13px;
  }
  @media (max-width: 600px) {
    gap: 7px;
    margin-bottom: 12px;
  }
}

.ach-card {
  background: rgba(54, 46, 97, 0.93);
  border-radius: 22px;
  padding: 15px 24px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  min-width: 190px;
  max-width: 250px;
  flex: 1 1 0px;
  height: auto;
  @media (max-width: 900px) {
    min-width: 0;
    max-width: none;
    padding: 13px 13px;
    border-radius: 18px;
  }
  @media (max-width: 600px) {
    padding: 7px 7px;
    border-radius: 13px;
  }
}
.ach-card.achievements {
  min-width: 320px;
  max-width: 350px;
  flex: 2 1 0px;
  @media (max-width: 900px) { min-width: 0; max-width: none;}
}

.ach-label {
  color: #fff;
  font-size: 20px;
  font-weight: 700;
  margin-bottom: 8px;
  @media (max-width: 900px) { font-size: 16px; margin-bottom: 5px;}
  @media (max-width: 600px) { font-size: 13px; margin-bottom: 4px;}
}
.achievements-list {
  display: flex;
  align-items: center;
  gap: 10px;
}
.ach-item {
  width: 33px;
  height: 33px;
  background: #53488e;
  border-radius: 7px;
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0.75;
  img {
    width: 28px;
    height: 28px;
    object-fit: cover;
    border-radius: 4px;
  }
  &.active { opacity: 1; }
  @media (max-width: 900px) { width: 24px; height: 24px; img { width: 18px; height: 18px; } }
  @media (max-width: 600px) { width: 16px; height: 16px; img { width: 11px; height: 11px; } }
}

.ach-value {
  width: 100%;
  display: flex;
  align-items: center;
  height: 34px;
  font-size: 24px;
  font-weight: 700;
  @media (max-width: 900px) { font-size: 18px; height: 22px;}
  @media (max-width: 600px) { font-size: 13px; height: 16px;}
}
.main-num {
  color: #be73fa;
  font-size: 26px;
  margin-right: 5px;
  font-weight: 700;
  @media (max-width: 900px) { font-size: 17px;}
  @media (max-width: 600px) { font-size: 12px;}
}
.main-sub {
  color: #b8aed4;
  opacity: 0.74;
  font-size: 22px;
  font-weight: 700;
  @media (max-width: 900px) { font-size: 13px;}
  @media (max-width: 600px) { font-size: 9px;}
}
.octo-gradient {
  font-size: 22px;
  font-weight: 800;
  background: linear-gradient(90deg, #be73fa 40%, #6ec8f2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-left: 3px;
  margin-right: 1px;
  letter-spacing: 0.01em;
  @media (max-width: 900px) { font-size: 14px; margin-left: 2px;}
  @media (max-width: 600px) { font-size: 9px; margin-left: 1px;}
}
.ach-card.balance .main-num { margin-right: 3px; }
.ach-card.balance .main-sub { margin-left: 2px; }
</style>
