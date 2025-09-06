<template>
  <section class="hero">
    <!-- Left -->
    <div class="hero_left">
      <div class="hero_left_title">
        <div class="hero_left_hello">Hello,</div>
        <div class="hero_left_login_status">you’re not logged in.</div>
        <button class="login_or_register">Login or register</button>
      </div>
      <div class="hero_left_subtitle">
        <div class="hero_left_subtitle_header">It’s free.</div>
        <div>
          Dive into the heart of chess with the FIDE Online Arena, the only online platform where
          chess aficionados can earn FIDE-recognized titles.
        </div>
      </div>
      <img class="pawn_image" src="../assets/pawn.png" />
    </div>

    <!-- Right -->
    <div class="hero_right">
      <div class="hero_right_question">Why play Chessgame?</div>
      <div class="hero_right_answer">
        Play rated games against opponents of your strength.<br />Get more hints in beginner
        games.<br />Store your games in the cloud.
      </div>
      <button class="login_or_register">Login or register</button>
    </div>
  </section>
</template>

<style scoped>
.hero {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  padding: 0 34px 0 34px;
  gap: 1rem;
  margin-top: 4rem;
}

.hero_left {
  background-color: var(--color-modal);
  height: 533px;
  padding: 27px;
  border-radius: 7px;
  box-sizing: border-box;
  position: relative;
  display: flex;
  flex-direction: column;
}

.hero_left_title {
  font-size: 60px;
  font-weight: bold;
  letter-spacing: -0.5%;
}

.hero_left_login_status {
  color: #00000066;
}

.hero_left_subtitle {
  margin-top: auto;
  margin-bottom: 0;
  width: 60%;
  font-size: 1rem;
  line-height: 22px;
}

.hero_left_subtitle_header {
  font-size: 1.125rem;
  font-weight: bold;
}

.pawn_image {
  position: absolute;
  bottom: 0;
  right: 0;
}

.hero_right {
  background-color: var(--color-modal);
  height: 533px;
  border-radius: 7px;
  font-size: 30px;
  line-height: 36px;
  padding: 27px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.hero_right_question {
  font-weight: bold;
  letter-spacing: -0.5%;
}

.hero_right_answer {
  letter-spacing: -3%;
  font-weight: regular;
  color: #00000066;
}

.login_or_register {
  border: none;
  background-color: var(--color-accent);
  font-size: 1rem;
  font-weight: bold;
  padding: 1rem 3rem;
  border-radius: 999px;
  margin-left: 0;
  margin-right: auto;
  margin-top: 1rem;
}
</style>
