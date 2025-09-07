<script setup>
import { ref } from 'vue'
const isOpen = ref(false)
</script>

<template>
  <header class="header">
    <button class="menu-toggle" @click="isOpen = true">
      <img src="../assets/menu.svg" width="40" height="40" alt="menu" />
    </button>

    <div class="nav" :class="{ open: isOpen }">
      <a><img src="../assets/home.svg" /></a>
      <a>Veřejné partie</a>
      <a>Turnaje</a>
      <a>Fórum</a>
      <a>ELO</a>
      <div class="mobile-actions">
        <button class="login"><img src="../assets/user.svg" />Přihlášení</button>
        <button class="notifications"><img src="../assets/notifications-unread.svg" /></button>
        <button class="new-game">
          <div>+</div>
          <div>Nová hra</div>
        </button>
      </div>
      <a class="close" @click="isOpen = false">Close</a>
    </div>
    <div class="logo"><img src="../assets/logo.png" /></div>
    <div class="actions">
      <button class="login"><img src="../assets/user.svg" />Přihlášení</button>
      <button class="notifications"><img src="../assets/notifications-unread.svg" /></button>
      <button class="new-game">
        <div>+</div>
        <div>Nová hra</div>
      </button>
    </div>
  </header>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.75rem 34px 0 34px;
  flex-wrap: wrap;
}

.menu-toggle {
  display: none;
  border: none;
  background: transparent;
  cursor: pointer;
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

.close {
  display: none;
  border: none;
  background: transparent;
  cursor: pointer;
}

.logo {
  position: absolute;
  top: 0.5rem;
  left: 50%;
  transform: translate(-50%, 0);
  height: 50px;
}

.logo img {
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

.mobile-actions {
  display: none;
  align-items: center;
  flex-direction: column;
  gap: 1rem;
}

.mobile-actions button {
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

@media (max-width: 1024px) {
  .nav {
    gap: 0.5rem;
  }

  .nav a {
    font-size: 0.75rem;
  }

  .logo {
    top: 1rem;
    height: 30px;
  }

  .logo img {
    height: 30px;
  }
}

@media (max-width: 768px) {
  .menu-toggle {
    display: block;
    position: absolute;
    top: 0.75rem;
    left: 0.75rem;
  }

  .close {
    display: block;
  }

  .mobile-actions {
    display: flex;
  }

  .nav {
    display: none;
    flex-direction: column;
    gap: 1rem;
    width: 100%;
    background: white;
    padding: 1rem;
  }

  .nav.open {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    justify-content: center;
    top: 0;
    left: 0;
    height: 100dvh;
    width: 100dvw;
    z-index: 1000;
    font-size: 2.5rem;
    padding: 0;
  }

  .header {
    flex-direction: row;
    flex-wrap: wrap;
  }

  .actions {
    display: none;
  }

  .logo {
    position: absolute;
    top: 1.5rem;
    left: 50%;
    transform: translate(-50%, 0);
    height: 20px;
  }

  .logo img {
    height: 20px;
  }
}
</style>
