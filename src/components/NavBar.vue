<script setup>
import { ref } from 'vue';
let isOpen = ref(false);

const toggleMenu = () => {
  isOpen = !isOpen;
  if (isOpen) {
  } else {
  }
};
</script>

<template>
  <div class="filter" :class="{ active: isOpen }" @click="isOpen = !isOpen"></div>
  <header class="flex-align">
    <div class="logo-container flex-align">
      <img src="../assets/desktop/logo.svg" alt="Creative Logo" class="logo" />
      <svg
        @click="isOpen = !isOpen"
        xmlns="http://www.w3.org/2000/svg"
        width="20"
        height="20"
        class="cross"
        :class="{ active: isOpen }"
      >
        <g fill-rule="evenodd" opacity=".5">
          <path d="M2.222.808l16.97 16.97-1.414 1.414L.808 2.222z" />
          <path d="M.808 17.778L17.778.808l1.414 1.414-16.97 16.97z" />
        </g>
      </svg>
      <svg
        @click="isOpen = !isOpen"
        width="24"
        height="18"
        xmlns="http://www.w3.org/2000/svg"
        class="burger"
        :class="{ active: !isOpen }"
      >
        <g fill="#000" fill-rule="evenodd" opacity=".5"><path d="M0 0h24v2H0zM0 8h24v2H0zM0 16h24v2H0z" /></g>
      </svg>
    </div>
    <nav :class="{ 'active-flex': isOpen }">
      <ul class="flex-align">
        <li class="list">About</li>
        <li class="list">Service</li>
        <li class="list">Projects</li>
        <li class="list-btn">Schedule a Call</li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
.filter {
  background-color: var(--clr-bg-black);
  opacity: 0;
  position: fixed;
  inset: 0;
  display: none;
  z-index: 99;
  animation: slideIn-2 0.7s forwards;
}

header {
  justify-content: space-between;
  position: relative;
}

.logo-container {
  justify-content: space-between;
}
.logo {
  width: 18rem;
}

.burger,
.cross {
  display: none;
  cursor: pointer;
}

.logo-container,
nav {
  flex: 1;
}

nav {
  background-color: var(--clr-red);
  padding: 5rem 0;
  display: grid;
  place-content: center;
}

ul {
  gap: 2rem;
}

li {
  font-size: var(--size-3);
  color: var(--clr-white);
  cursor: pointer;
  padding-block: 0.5rem;
}

.list:hover {
  border-bottom: 1px solid rgb(240, 240, 240);
}

.list-btn {
  background-color: var(--clr-bg-black);
  padding: 1.5rem 2.5rem;
  margin-left: 2rem;
}

.list-btn:hover {
  background-color: rgb(60, 61, 65);
}
@media screen and (max-width: 1440px) {
  header {
    gap: 5rem;
  }
  nav {
    flex: unset;
  }
  nav {
    width: 75%;
  }
  .list-btn {
    margin-left: 1.5rem;
  }
  .logo {
    min-width: 13rem;
  }
}

@media screen and (max-width: 1024px) {
  ul {
    gap: 1rem;
  }
  .list-btn {
    padding: 1.5rem;
    margin-left: 1rem;
  }
}
@media screen and (max-width: 800px) {
  header {
    padding-block: 2.5rem;
  }
  nav {
    display: none;
    background-color: var(--clr-bg-black);
    position: fixed;
    z-index: 100;
    top: 7.45rem;
    right: 1rem;
    width: 65%;
    padding: 4rem 0;
    animation: slideIn 0.7s forwards;
  }
  .logo {
    min-width: unset;
    width: 13rem;
  }
  ul {
    flex-direction: column;
    gap: 0.5rem;
  }

  .list-btn {
    background-color: var(--clr-red);
    margin-top: 1rem;
  }
  .active {
    display: inline-block;
  }
  .active-flex {
    display: grid;
  }
}
</style>
