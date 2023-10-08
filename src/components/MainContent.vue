<template>
  <main>
    <section class="main-content">
      <div class="col-1">
        <img src="../assets/mobile/image-strategic.jpg" alt="A Computer" class="col-1-img" />
        <img src="../assets/desktop/bg-pattern-wave-red.svg" alt="#" id="wave" />
      </div>
      <div class="col-2">
        <div class="col-2-txt">
          <h2><strong>Design</strong> is strategic</h2>
          <p>
            “A well-crafted design strategy consistently produces desired outcomes and brand awareness. We are firm believers that
            success lies in creative collaboration with our clients.”
          </p>
          <button class="btn-3">Schedule a Call</button>
        </div>
      </div>
    </section>
    <section class="approach">
      <h3>Our approach for creating a winning brand</h3>
      <ol>
        <li id="li-1">
          <h4>
            <p class="nb">01</p>
            Brand Strategy
          </h4>
          <p class="ol-p">
            Brand strategy is critical for long-term success. Outshining competitors and capturing the target audience are key.
          </p>
        </li>
        <li>
          <h4>
            <p class="nb">02</p>
            Brand Design
          </h4>
          <p class="ol-p">
            Keeping the brand design unique and meaningful helps in communicating the brand’s timeless value effectively.
          </p>
        </li>
        <li>
          <h4>
            <p class="nb">03</p>
            Web Design
          </h4>
          <p class="ol-p">
            A beautifully crafted website is the best tool for brand awareness, and ultimately results in increased revenues.
          </p>
        </li>
      </ol>
    </section>
  </main>
</template>

<style scoped>
.main-content {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 1fr;
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  height: 61.5rem;
  isolation: isolate;
}

.col-1 {
  background-image: url('../assets/desktop/image-strategic.jpg');
  background-size: cover;
  position: relative;
}

.col-2 {
  background-color: var(--clr-bg-black);
  display: grid;
  place-content: center;
}

#wave {
  position: absolute;
  top: 50%;
  right: -4rem;
  transform: translateY(-50%);
  z-index: 0;
}

.col-1-img {
  display: none;
  width: 100%;
  object-fit: cover;
}
h2 {
  color: var(--clr-white);
  max-width: 25.625rem;
}
h2 strong {
  color: var(--clr-red);
}

.col-2 p {
  color: var(--clr-white);
  max-width: 27.813rem;
  margin-block: 3rem;
  z-index: 1;
  position: relative;
}

.approach {
  height: 68.75rem;
  background-color: var(--clr-red);
  display: grid;
  place-content: center;
  width: 60%;
  min-width: 850px;
  margin-left: auto;
  position: relative;
  top: -10rem;
}

h3 {
  font-size: var(--size-2);
  max-width: 33.75rem;
  line-height: var(--size-2);
  position: absolute;
  top: 30rem;
  left: -23.7rem;
  transform: translateY(-50%);
}

li {
  margin-block: 6rem;
}

.nb {
  font-size: 80px;
  color: var(--clr-white);
  opacity: 0.4;
  font-weight: 800;
  position: absolute;
  top: -1.3rem;
  left: -3.8rem;
}

h4 {
  font-size: var(--size-3);
  font-weight: bold;
  color: var(--clr-white);
  margin-bottom: 1.2rem;
  position: relative;
}

.ol-p {
  color: var(--clr-white);
  max-width: 27.813rem;
  opacity: 0.8;
  font-size: var(--size-4);
}

@media screen and (max-width: 1325px) {
  .approach {
    min-width: 650px;
    height: 49.8rem;
  }
  h3 {
    font-size: 32px;
    max-width: 17.563rem;
    line-height: 40px;
    position: absolute;
    top: 29rem;
    left: -18rem;
    transform: translateY(-50%);
  }
  #wave {
    width: 7rem;
  }
}

@media screen and (max-width: 1024px) {
  .main-content {
    height: 41.125rem;
  }
  .col-2 {
    padding-inline: 2rem;
    padding-top: 5rem;
    display: initial;
  }
  h2 {
    font-size: 32px;
    line-height: 40px;
    max-width: 16rem;
  }
  .col-2 p {
    margin-block: 2rem;
  }
  .approach {
    min-width: 550px;
    height: 49.8rem;
  }
  .nb {
    left: -1rem;
  }
    #wave {
    width: 5rem;
     right: -2.5rem;
  }
}

@media screen and (max-width: 880px) {
  .main-content {
    display: flex;
    flex-direction: column;
    height: fit-content;
    margin-top: 4rem;
  }

  .col-2 {
    padding-top: 0rem;
    padding-block: 3rem;
  }

  .col-1 {
    background-image: none;
  }

  #wave {
    top: unset;
    right: unset;
    left: 2rem;
    transform: translateY(0);
    bottom: -1rem;
    z-index: 0;
  }

  .col-1-img {
    display: block;
    width: 100%;
    object-fit: cover;
  }

  h3 {
    color: var(--clr-white);
    position: initial;
    transform: translateY(0);
    margin-top: 2rem;
  }

  .approach {
    height: fit-content;
    position: initial;
    width: 100%;
    min-width: unset;
    padding-left: 2rem;
  }
}
</style>
