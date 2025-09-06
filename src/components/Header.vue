<template>
  <header class="header">
    <div class="nav">
        <a><img src="../assets/home.svg"/></a>
        <a>Veřejné partie</a>
        <a>Turnaje</a>
        <a>Fórum</a>
        <a>ELO</a>
    </div>
    <div class="logo"><img src="../assets/logo.png" height="50px"/></div>
    <div class="actions">
      <button class="login"><img src="../assets/user.svg"/>Přihlášení</button>
      <button class="notifications"><img src="../assets/notifications-unread.svg"/></button>
      <button class="new-game"><div>+</div><div>Nová hra</div></button>
    </div>
  </header>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.75rem 34px 0 34px;
  width: 100%;
}

.nav {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 1.5rem;
}

.nav a {
  font-size: 1rem;
  font-family: sans-serif;
  font-weight: bold;
  cursor: pointer;
}

.logo {
  height: 50px;
}

.actions {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.actions button {
  border: none;
  cursor: pointer;
  display: flex;
  background-color: #00000000;
  flex-direction: row;
  align-items: center;
  gap: 1rem;
  font-weight: bold;

}

.new-game {
  background-color: var(--color-accent) !important;
  border: none;
  padding: 0.75rem;
  border-radius: 999px;
}

</style>
