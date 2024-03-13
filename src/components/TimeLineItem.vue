<script setup>
  const props = defineProps({
    time: {
      type: String,
      required: true,
    },
    heading: {
      type: String,
      required: true,
    },
    location: {
      type: String,
      required: true,
    },
    locationLink: {
      type: String,
      required: true,
    },
  })
</script>

<template>
  <div class="main-container">

  <div>
    <div class="heading"> {{props.heading}}</div>
    <a :href="props.locationLink" target="_blank"> {{props.location}}</a>
  </div>
  <div>
    <div>{{props.time}}</div>
  </div>
  </div>
</template>

<style scoped>
  .main-container{
    display: flex;
    justify-content: space-between;
    border: 1px solid var(--color-border);
    padding: 5px 15px;
    border-radius: 5px;
    margin-bottom: 10px;
  }
  .heading{
    font-size: 1.2rem;
    font-weight: 500;
    margin-bottom: 0.4rem;
    color: var(--color-heading);
  }
  a{
    font-style: italic;
  }
</style>