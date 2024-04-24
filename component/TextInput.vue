<template>
  <div class="text-input-shift-wrapper">
    <input id="input" type="text" class="text-input" placeholder="" v-model="model" @keyup.enter="emit('submit')">
    <label for="input">{{ label }}</label>
  </div>
</template>

<script setup lang="ts">

export interface Props {
  label?: string;
}
const props = withDefaults(defineProps<Props>(), {
  label: ""
});
const model = defineModel<string>();
const emit = defineEmits<{
  submit: [void]
}>();

</script>
