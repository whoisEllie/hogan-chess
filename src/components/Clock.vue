<script>
export default {
  name: 'Clock',
  data() {
    return {
      now: new Date(),
      timerId: null,
    }
  },
  computed: {
    secondDeg() {
      return this.now.getSeconds() * 6
    },
    minuteDeg() {
      return this.now.getMinutes() * 6 + this.now.getSeconds() * 0.1
    },
    hourDeg() {
      return (this.now.getHours() % 12) * 30 + this.now.getMinutes() * 0.5
    },
  },
  mounted() {
    this.timerId = setInterval(() => {
      this.now = new Date()
    }, 1000)
  },
  beforeUnmount() {
    clearInterval(this.timerId)
  },
}
</script>

<template>
  <div class="clock">
    <img src="../assets/clock.svg" />
    <div class="hand hour" :style="{ transform: `rotate(${hourDeg}deg)` }"></div>
    <div class="hand minute" :style="{ transform: `rotate(${minuteDeg}deg)` }">
      <div class="minute-style"></div>
    </div>
    <div class="hand second" :style="{ transform: `rotate(${secondDeg}deg)` }">
      <div class="second-style"></div>
    </div>
    <div class="center"></div>
  </div>
</template>

<style scoped>
.clock {
  position: relative;
  width: 128px;
  height: 128px;
  margin: 2rem auto;
  background: #000;
}

.hand {
  position: absolute;
  bottom: 50%;
  left: 50%;
  transform-origin: bottom center;
}

.hand.hour {
  width: 3px;
  height: 35px;
  background-color: #dfddd2;
  margin-left: -1.5px;
}

.hand.minute {
  width: 2px;
  height: 55px;
  margin-left: -1px;
}

.minute-style {
  height: 45px;
  width: 2px;
  background-color: #dfddd2;
}

.hand.second {
  width: 2px;
  height: 55px;
  margin-left: -1px;
}

.second-style {
  height: 70px;
  width: 2px;
  background-color: var(--color-accent);
}

.center {
  position: absolute;
  width: 3px;
  height: 3px;
  background-color: var(--color-accent);
  border-radius: 50%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
