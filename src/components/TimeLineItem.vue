<script setup>
import MoreIcon from "@/components/icons/MoreIcon.vue";
import {ref} from "vue";
import Badge from "@/components/Badge.vue";

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
  extraInformation: {
    type: Array,
    required: false,
  },
  skills: {
    type: Array,
    required: false,
  },
})

const expand = ref(false);


</script>

<template>
  <div class="main-container" @click="()=>expand = !expand">
    <div class="heading">
      {{ props.heading }}
      <div class="time-container">
        <div>{{ props.time }}</div>
      </div>
    </div>


    <div class="expanded-section" :class="{'expanded-section-active':expand}">
      <p v-for="info in props.extraInformation" :key="info">
        {{ info }}
      </p>
    </div>
    <div>
      <badge v-for="skill in props.skills" :content="skill" :key="skill" size="small"></badge>

    </div>
    <div>
      <a :href="props.locationLink" target="_blank"> {{ props.location }}</a>

    </div>
    <div class="expand-icon" v-if="!!props.extraInformation?.length">
      <MoreIcon/>
    </div>
  </div>
</template>

<style scoped>
.main-container {
  position: relative;
  display: flex;
  flex-direction: column;
  border: 1px solid var(--color-border);
  padding: 5px 15px;
  border-radius: 5px;
  margin-bottom: 10px;
  cursor: pointer;
}

.main-container:hover {
  transition: border-color 0.3s;
  border-color: var(--color-border-hover);
}

.heading {
  font-size: 1.1rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
  color: var(--color-heading);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

a {
  font-style: italic;
}

.expand-icon {
  position: absolute;
  right: 10px;
  bottom: 0;
}

.time-container {
  color: var(--color-text);

  min-width: 140px;
  font-size: 0.9rem;
  font-weight: 300;
}

.expanded-section {
  max-height: 0;
  overflow: hidden; /* Changed from visibility */
  transition: max-height 0.3s;
}

.expanded-section-active {
  max-height: 400px; /* Set an appropriate maximum height here */
}

p {
  margin-bottom: 5px;
}
</style>