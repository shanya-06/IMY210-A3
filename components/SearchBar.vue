<script setup>
defineProps({ modelValue: String });
defineEmits(["update:modelValue", "search"]);
</script>

<template>
  <div style="margin-bottom: 1rem;">
    <input
      type="text"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
      placeholder="Search blogs..."
      style="padding: 0.5rem; border: 1px solid #ccc; border-radius: 4px;"
    />
    <button
      @click="$emit('search')"
      style="margin-left: 0.5rem; padding: 0.5rem 1rem; background: #0070f3; color: white; border: none; border-radius: 4px;"
    >
      Search
    </button>
  </div>
</template>
