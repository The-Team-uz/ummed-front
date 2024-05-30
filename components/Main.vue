<script setup>
const { t } = useI18n();
const day = ref("");
const month = ref("");
const weekday = ref("");
const year = ref("");
const week = ref([]);

const updateTime = () => {
  const now = new Date();
  day.value = now.getDate().toString();
  month.value = now.toLocaleString("default", { month: "long" });
  weekday.value = now.toLocaleString("default", { weekday: "short" });
  year.value = now.getFullYear().toString();

  fillWeekDates(now);
};

const fillWeekDates = (currentDate) => {
  const daysOfWeek = ["mon", "thu", "wen", "thr", "fri", "sat", "sun"];
  const currentDayIndex = (currentDate.getDay() + 6) % 7;
  week.value = [];

  for (let i = 0; i < 7; i++) {
    const tempDate = new Date(currentDate);
    tempDate.setDate(currentDate.getDate() + (i - currentDayIndex));

    const isActive =
      tempDate.toDateString() === currentDate.toDateString() ? "true" : "false";

    week.value.push({
      day: daysOfWeek[tempDate.getDay() === 0 ? 6 : tempDate.getDay() - 1],
      date: tempDate.getDate().toString(),
      status: isActive,
    });
  }
};

onMounted(() => {
  updateTime();
});
</script>

<template>
  <div class="wrapperr" data-aos="fade-up">
    <div class="wrapper-leftt">
      <div class="title-11">
        {{ t("main-title") }}
      </div>
      <div class="title-22">
        {{ t("main-text") }}
      </div>
    </div>
    <div class="wrapper-rightt">
      <div class="titlee">
        <div v-for="i in 3" class="title-rr">
          <div class="p">ummed</div>
          <span>®</span>
        </div>
      </div>
      <img src="~/assets/images/asbob.jpg" alt="" class="img" />
      <div class="calendarr">
        <div class="month-yearr">{{ t(month) }},&nbsp;{{ year }}</div>
        <div class="weekk">
          <div
            class="weekdayy"
            v-for="i in week"
            :class="i.status == 'true' ? 'active' : ''"
          >
            <div class="dayy">{{ t(i.day) }}</div>
            <div class="datee">{{ i.date }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "~/assets/mixins.scss";
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.wrapperr {
  width: 100%;
  padding: 0 10px;
  display: block;
  @include breakpoint(lg) {
    // margin-left: 15px;
    display: flex;
    justify-content: space-between;
  }
  .wrapper-leftt {
    width: 100%;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 300px;
    @include breakpoint(xs) {
      height: 400px;
    }
    gap: 40px;
    @include breakpoint(lg) {
      text-align: start;
      align-items: start;
      width: calc(100% / 2);
      height: 670px;
    }
    .title-11 {
      font-weight: 700;
      color: #000;
      line-height: 1em;
      font-size: 30px;
      @include breakpoint(xs) {
        width: 500px;
        font-size: 40px;
      }
      @include breakpoint(md) {
        font-size: 60px;
        width: 800px;
      }
      @include breakpoint(lg) {
        width: 500px;
      }
    }
    .title-22 {
      color: #676c80;
      margin-top: -20px;
      margin-bottom: 10px;
      line-height: 1.5em;
      @include breakpoint(xs) {
        width: 500px;
      }
      @include breakpoint(md) {
        font-size: 20px;
        width: 600px;
      }
      @include breakpoint(lg) {
        max-width: 500px;
      }
    }
  }
  .wrapper-rightt {
    position: relative;
    width: 100%;
    display: flex;
    justify-content: center;
    @include breakpoint(lg) {
      width: 45%;
      height: 670px;
    }
    .titlee {
      border: 1px solid #fff !important;
      position: absolute;
      margin-top: 60px;
      position: absolute;
      bottom: auto;
      right: auto;
      color: #000;
      font-weight: 600;
      line-height: 23px;
      background-color: rgba(250, 250, 250, 0.3);
      backdrop-filter: blur(20px);
      width: 184px;
      border-radius: 20px;
      padding: 10px 0;
      display: flex;
      align-items: center;
      flex-direction: column;
      box-shadow: 0 0 2px 0.8px rgba(129, 129, 129, 0.2);
      left: 10%;
      top: 23%;
      @include breakpoint(lg) {
        left: -18%;
      }
      .title-rr {
        display: flex;
      }
      span {
        font-weight: 800;
        font-size: 14px;
      }
    }
    .img {
      width: 500px;
      border-radius: 20px;
      @include breakpoint(lg) {
        height: 600px;
      }
      @include breakpoint(xl) {
        width: 100%;
        height: 720px;
      }
    }
    .calendarr {
      position: absolute;
      background-color: #ffd8cbaf;
      border-radius: 2rem;
      box-shadow: 0 0 2px 0.8px rgba(129, 129, 129, 0.2);
      top: 50%;
      right: 10%;
      height: 140px;
      width: 240px;
      @include breakpoint(md) {
        height: 140px;
        width: 300px;
      }
      @include breakpoint(lg) {
        right: 10px;
        width: 340px;
        top: 20%;
        height: 150px;
      }
      @include breakpoint(xl) {
        top: 60%;
        right: -20%;
      }
      .month-yearr {
        text-transform: capitalize;
        display: block !important;
        height: 30px;
        color: #000;
        padding: 25px 20px;
        font-size: 14px;
        @include breakpoint(md) {
          font-size: 18px;
        }
      }
      .weekk {
        padding: 10px 20px;
        display: flex;
        justify-content: space-between;
        text-align: center;
        font-size: 8px;
        line-height: 1.5;
        @include breakpoint(md) {
          font-size: 12px;
        }
        .weekdayy {
          padding: 16px 5px;
          color: #000;
          font-weight: 500;
          .dayy {
            text-transform: uppercase;
            letter-spacing: 1.5px;
            line-height: 20px;
          }
        }
      }
      .active {
        width: 40px;
        background-color: #fe5722;
        color: #fff !important;
        font-weight: 600 !important;
        border-radius: 20px;
        box-shadow: 0 0 8px 1px rgba(68, 68, 68, 0.2);
      }
    }
  }
}

@media (max-width: 500px) {
  .titlee {
    margin-top: 20px !important;
    left: -2% !important;
    width: 120px !important;
    height: 60px !important;
    font-size: 12px !important;
    line-height: 1 !important;
    span {
        font-weight: 800;
        font-size: 11px !important;
      }
  }
  .calendarr {
    right: 0% !important;
  }
}
</style>
