<script setup></script>

<template>
  <section class="hero">
    <img src="../assets/mobile/image-hero.jpg" alt="Workers Image" class="hero-img" />
    <div class="hero-txt">
      <h1>Branding & website design agency</h1>
      <p>
        We specialize in visual storytelling by creating cohesive brand and website design solutions for small businesses, giving
        lasting impressions to audiences in a digital world.
      </p>
      <button class="btn-1">Learn More</button>
    </div>
  </section>
</template>

<style scoped>
.hero {
  background-color: var(--clr-white);
  background-image: url('../assets/desktop/image-hero.jpg');
  background-position: right;
  padding-block: 8rem;
  height: 800px;
}

.hero-txt {
  max-width: 45.625rem;
}

p {
  padding-block: 2rem;
  max-width: 33.75rem;
}
.hero-img {
  display: none;
}
@media screen and (max-width: 1024px) {
  .hero {
    background-image: url('../assets/tablet/image-hero.jpg');
    padding-block: 6rem;
    height: 37.875rem;
  }
}

@media screen and (max-width: 800px) {
  .hero {
    background-image: none;
    padding-block: 0;
    height: auto;
  }
  .hero-img {
    display: block;
    width: 100%;
    object-fit: cover;
    margin-bottom: 2rem;
  }
}
</style>
