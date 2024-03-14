<script setup>
defineProps({
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">Miguel Monteiro</h1>
    <h3>
      IoT Software Engineer
    </h3>
    <a href="https://www.linkedin.com/in/mmonteiroc/" target="_blank" rel="noopener">LinkedIn</a>
    <a href="https://github.com/mmonteiroc" target="_blank" rel="noopener">Github</a>

  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-wrap: nowrap;
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
a{
  margin-right: 5px;
}
</style>
