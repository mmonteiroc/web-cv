<script setup>
import TimeLineContainer from './TimeLineContainer.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import TimeLineItem from "@/components/TimeLineItem.vue";
import ExperienceIcon from "@/components/icons/ExperienceIcon.vue";
import Badge from "@/components/Badge.vue";
import LocalizationIcon from "@/components/icons/LocalizationIcon.vue";
import ToolIcon from "@/components/icons/ToolIcon.vue";
import IconEcosystem from "@/components/icons/IconEcosystem.vue";
import {educations, experiences, softSkills, techSkills} from "@/constants.js";
</script>

<template>
  <TimeLineContainer>
    <template #icon>
      <ExperienceIcon/>
    </template>
    <template #heading>Professional experience</template>

    <TimeLineItem
        v-for="experience in experiences"
        :key="experience.location"
        :location="experience.location"
        :heading="experience.heading"
        :time="experience.time"
        :location-link="experience.locationLink"
    >
    </TimeLineItem>

  </TimeLineContainer>


  <TimeLineContainer>
    <template #icon>
      <DocumentationIcon/>
    </template>
    <template #heading>Education</template>

    <TimeLineItem
        v-for="education in educations"
        :key="education.location"
        :location="education.location"
        :heading="education.heading"
        :time="education.time"
        :location-link="education.locationLink"
    >
    </TimeLineItem>
  </TimeLineContainer>

  <TimeLineContainer>
    <template #icon>
      <ToolIcon/>
    </template>
    <template #heading>Technical skills</template>
    <Badge v-for="skill in techSkills" :content="skill" :key="skill"></Badge>
  </TimeLineContainer>

  <TimeLineContainer>
    <template #icon>
      <IconEcosystem/>
    </template>
    <template #heading>Soft skills</template>
    <Badge v-for="skill in softSkills" :content="skill" :key="skill"></Badge>
  </TimeLineContainer>


  <TimeLineContainer>
    <template #icon>
      <LocalizationIcon/>
    </template>
    <template #heading>Languages</template>
    <Badge content="Spanish - Native"></Badge>
    <Badge content="Portuguese - Native"></Badge>
    <Badge content="English - C2"></Badge>
    <Badge content="French - B2"></Badge>
  </TimeLineContainer>
</template>
