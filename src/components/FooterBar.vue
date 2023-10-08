<template>
  <footer class="flex-align">
    <h2>Let's build something great together.</h2>
    <button class="btn-1">Schedule a Call</button>
  </footer>
</template>

<style scoped>
footer {
  justify-content: space-between;
  padding-bottom: 3rem;
  padding-inline: 6rem;
  background-image: url('../assets/desktop/bg-pattern-wave-red.svg');
  background-position-x: -4rem;
}

@media screen and (max-width: 1024px) {
  footer {
    flex-direction: column;
    background-image: none;
    padding-block: 3rem;
  }
  button {
    margin-top: 2rem;
  }
  h2 {
    font-size: 32px;
    line-height: 40px;
    text-align: center;
  }
}
</style>
