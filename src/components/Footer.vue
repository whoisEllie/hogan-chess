<script>
import Clock from './Clock.vue'

export default {
  components: { Clock },
  data() {
    return {
      now: new Date(),
    }
  },
  computed: {
    getTime() {
      let time = this.now.toLocaleTimeString(navigator.language, {hour: "2-digit", minute:
        "2-digit", hour12: false});
      console.log(time);
      return time;
    },
    getDay() {
      return this.now.toLocaleDateString(navigator.language, {weekday: "long"});
    },
    getDate() {
      return this.now.toLocaleDateString(navigator.language);
    },
    getCity() {
      return "Čestmír"; //TODO: Geolocation implementation
    }
  }
}
</script>

<template>
  <footer class="wrapper">
    <div class="clock-wrapper">
      <div class="digital-clock">
        <div class="time">{{getTime}}</div>
        <div class="details">
          <div>{{getDay}}</div>
          <div>{{getDate}}</div>
          <div style="color: #dfddd299">{{getCity}}</div>
        </div>
      </div>
      <Clock class="analogue-clock" />
    </div>

    <div class="footer">
      <div class="user-card">
        <img src="../assets/pfp.png" alt="User avatar" class="avatar" />
        <div class="user-details">
          <div class="name">David Rychlý</div>
          <div class="rating">(1578)</div>
        </div>
      </div>


      <div class="footer-nav">
        <a>Moje partie</a>
        <a>Rozehrané partie</a>
        <a class="with-dot">Potvrzení výzvy</a>
        <a>Turnaj</a>
        <button class="new-game">
          <div>+</div>
          <div>Nová hra</div>
        </button>
      </div>

    </div>
  </footer>
</template>

<style scoped>
.wrapper {
  width: calc(100vw - 69px);
  position: absolute;
  bottom: 34px;
  left: 50%;
  transform: translate(-50%, 0);
  display: flex;
  flex-direction: column;
  gap: 27px;
}

.clock-wrapper {
  border-radius: 7px;
  background: #000000;
  height: 159px;
  width: 371px;
  display: flex;
  align-items: center;
  padding: 1rem 1rem 1rem 1rem;
  box-sizing: border-box;
  align-self: flex-end;
}

.digital-clock {
  color: #dfddd2;
  display: flex;
  justify-content: space-between;
  font-size: 1rem;
  font-weight: bold;
  flex-direction: column;
  height: 100%;
}

.time {
  font-size: 55px;
}

.details {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.analogue-clock {
  margin-left: auto;
  margin-right: 0;
}

.footer {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  height: 73px;
  border-radius: 7px;
  overflow: hidden;
  background: #ffffff;
  padding: 0.75rem;
  box-sizing: border-box;
}

.user-card {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 1rem;
  font-size: 20px;
  font-weight: bold;
}

.rating {
  color: #00000066;
}

.user-card img {
  width: 49px;
  height: 49px;
  border-radius: 999px;
}

.footer-nav {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 1.5rem;
}

.footer-nav a {
  font-size: 1rem;
  font-family: sans-serif;
  font-weight: bold;
  cursor: pointer;
}

.new-game {
  border: none;
  cursor: pointer;
  display: flex;
  background-color: #00000000;
  flex-direction: row;
  align-items: center;
  gap: 1rem;
  font-weight: bold;
  background-color: var(--color-accent) !important;
  border: none;
  padding: 0.75rem;
  border-radius: 999px;
}

.with-dot {
  position: relative;
}

.with-dot::after {
  content: '';
  position: absolute;
  top: -2px;
  right: -12px;
  width: 6px;
  height: 6px;
  background-color: var(--color-accent) !important;
  border-radius: 999px;
}

</style>
