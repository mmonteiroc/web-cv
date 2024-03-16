<template>
  <div class="item">
    <i>
      <slot name="icon"></slot>
    </i>
    <div class="details">
      <h3 class="heading">
        <slot name="heading"></slot>
        <div class="top-border">&nbsp;</div>

      </h3>
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>

.heading{
  position: relative;
}

.top-border{
  width: 0;
  height: 2px;
  background-color: var(--color-green);
  transition: width 0.5s ease-in;
}

.item {
  margin-top: 2rem;
  display: flex;
  position: relative;
}

.details {
  flex: 1;
  margin-left: 1rem;
}

i {
  display: flex;
  place-items: center;
  place-content: center;
  width: 32px;
  height: 32px;

  color: var(--color-text);
}

h3.heading {
  font-size: 1.6rem;
  font-style: italic;
  font-weight: 500;
  margin-bottom: 0.4rem;
  color: var(--color-heading);
}

@media (min-width: 1024px) {
  .item {
    margin-top: 0;
    padding: 0.4rem 0 1rem calc(var(--section-gap) / 2.5);
  }

  .item:hover i, .item:hover .heading {
    transition: border 0.3s, color 0.3s;
  }

  .item:hover .top-border{
    width: 100%;
  }

  .item:hover i{
    border: 1px solid var(--color-green);
    color: var(--color-green);
  }

  .item:hover .heading {
    color: var(--color-green);
  }

  i {
    left: 0;
    position: absolute;
    border: 1px solid #898989;

    background: var(--color-background);
    border-radius: 8px;
    width: 50px;
    height: 50px;
  }

  .item:after {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 25px;
    top: 56px;
    height: 100%;
  }

  .item:first-of-type:before {
    display: none;
  }

  .item:last-of-type:after {
    display: none;
  }
}
</style>
<script setup>
</script>