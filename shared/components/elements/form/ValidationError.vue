<script setup>
const props = defineProps({
  errors: { type: Object, required: true },
  name: { type: String, required: true },
})

const hasErrors = computed(() => props.name in props.errors.value)
</script>

<template>
  <div v-if="hasErrors">
    <div
      v-for="error in errors.value[name]"
      :key="name + error"
      class="mt-1 rounded-lg bg-red-100 px-4 py-1 text-sm text-red-800"
      v-text="error"
    />
  </div>
</template>
