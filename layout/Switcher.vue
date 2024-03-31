<template>
  <div class="switcher">
    <slot/>
  </div>
</template>

<script lang="ts" setup>

interface SwitcherProps {
  limit?: number,
  space?: string,
  threshold: string
}

const props = withDefaults(defineProps<SwitcherProps>(), {
  limit: 10,
  space: ""
});

// const props = defineProps<{
//   limit: {
//     required: false,
//     type: number,
//     default: 10,
//   },
//   space: {
//     required: false,
//     type: string,
//     default: "",
//   },
//   threshold: {
//     required: true,
//     type: string,
//   },
// }>()
</script>

<style>

.switcher {
  display: flex;
  flex-wrap: wrap;
  gap: v-bind("props.space");
}

.switcher > * {
  width: 100%;
  flex-grow: 1;
  flex-basis: calc((v-bind("props.threshold") - 100%) * 999);
}

</style>
