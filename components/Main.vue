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
  <div class="wrapperr nav-container" data-aos="fade-up">
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
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.wrapperr {
  display: flex;
  justify-content: space-between;
  width: 100%;
  margin-left: 15px;
  .wrapper-leftt {
    width: calc(100% / 2);
    height: 670px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    // justify-content: space-around;
    gap: 40px;
    .title-11 {
      width: 500px;
      font-size: 60px;
      font-weight: 700;
      color: #000;
      line-height: 1em;
    }
    .title-22 {
      max-width: 500px;
      font-size: 20px;
      color: #676c80;
      margin-top: -20px;
      margin-bottom: 10px;
      line-height: 1.5em;
    }
  }
  .wrapper-rightt {
    position: relative;
    width: 45%;
    height: 670px;
    .titlee {
      border: 1px solid #fff !important;
      position: absolute;
      margin-top: 60px;
      position: absolute;
      bottom: auto;
      left: -18%;
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
      height: 720px;
      border-radius: 20px;
    }
    .calendarr {
      position: absolute;
      top: 25%;
      right: -20%;
      width: 340px;
      height: 150px;
      background-color: #ffd8cbaf;
      border-radius: 2rem;
      box-shadow: 0 0 2px 0.8px rgba(129, 129, 129, 0.2);
      .month-yearr {
        padding: 25px 20px;
        font-size: 18px;
        text-transform: capitalize;
        display: block !important;
        height: 30px;
        color: #000;
      }
      .weekk {
        padding: 10px 20px;
        display: flex;
        justify-content: space-between;
        text-align: center;
        font-size: 12px;
        line-height: 1.5;
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
        background-color: #fe5722;
        color: #fff !important;
        font-weight: 600 !important;
        border-radius: 20px;
        box-shadow: 0 0 8px 1px rgba(68, 68, 68, 0.2);
      }
    }
  }
}
</style>
