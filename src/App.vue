<script setup>
import TheWelcome from './components/TheWelcome.vue'
import ProfilePresentation from "@/components/ProfilePresentation.vue";
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/profile-image.png"/>

    <div class="wrapper">
      <ProfilePresentation/>
    </div>
  </header>

  <main>
    <TheWelcome/>
  </main>

  <a href="/assets/Miguel-Monteiro-Claveri_resume.pdf" target="_blank" class="pdf-button">Download PDF version</a>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;

  max-width: 230px;
  border-radius: 50%;
  border: solid 1px var(--color-border);
}

@media (min-width: 1026px) {
  main {
    max-height: 850px;
    overflow-y: auto;
    overflow-x: unset;
    direction: rtl;
  }
}

@media (min-width: 1480px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 3);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

.pdf-button{
  position: fixed;
  bottom: 20px;
  left: 20px;
  cursor: pointer;
  padding: 10px;
  border-radius: 5px;
  border: dashed 1px var(--color-green);
  z-index: 100;
  background-color: var(--color-background);
}
</style>
