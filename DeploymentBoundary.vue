<script setup lang="ts">
import {computed, type Component, type PropType} from 'vue'

const props = defineProps({
  selfHost: {
    type: Object as PropType<Component>,
    required: true
  },
  fallback: {
    type: Object as PropType<Component>,
    required: true
  }
})

const deploymentMode = import.meta.env.VITE_DEPLOYMENT_MODE

const targetComponent = computed(() =>
    deploymentMode === 'self-host' ? props.selfHost : props.fallback
)
</script>

<template>
  <component
      :is="targetComponent"
      v-bind="$attrs"
  >
    <template
        v-for="(_, name) in $slots"
        #[name]="slotProps"
    >
      <slot :name="name" v-bind="slotProps" />
    </template>
  </component>
</template>
