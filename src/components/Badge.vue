<template>
  <span class="badge" :class="computedClasses">
    {{ content }}
    <slot /> </span>
</template>

<script setup>
import { computed } from 'vue';

const props = defineProps({
  content: {
    type: [String, Number],
    default: ''
  },
  type: {
    type: String,
    default: 'default',
    validator: (value) => ['default', 'success', 'warning', 'error'].includes(value)
  },
  size: {
    type: String,
    default: 'medium',
    validator: (value) => ['small', 'medium', 'large'].includes(value)
  }
});

const computedClasses = computed(() => {
  return {
    'badge-success': props.type === 'success',
    'badge-warning': props.type === 'warning',
    'badge-error': props.type === 'error',
    'badge-small': props.size === 'small',
    'badge-medium': props.size === 'medium',
    'badge-large': props.size === 'large',
  }
});
</script>

<style scoped>
.badge {
  margin-right: 10px;
  margin-bottom: 7px;
  display: inline-block;
  padding: 0.3em 0.7em;
  border-radius: 10px;
  font-size: 14px;
  font-weight: 600;
  text-align: center;
  white-space: nowrap;
  background-color: transparent; /* Default color */
  color: var(--color-text);
  border: 1px solid var(--color-border);
}

.badge:hover{
  background-color: var(--color-border);
}

.badge-success { background-color: #4caf50; color: white; }
.badge-warning { background-color: #ffc107; }
.badge-error { background-color: #f44336; color: white; }

.badge-small { font-size: 10px; border-radius: 7px }
.badge-medium { font-size: 12px; }
.badge-large { font-size: 14px; }
</style>