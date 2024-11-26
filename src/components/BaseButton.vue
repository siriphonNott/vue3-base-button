<script setup lang="ts">
import { computed } from "vue";
type BaseButtonProps = {
  id?: string;
  size?: number;
  textColor?: string;
  color?: string;
  border?: string;
  padding?: string;
};

const props = withDefaults(defineProps<BaseButtonProps>(), {
  id: "",
  size: 16,
  textColor: "black",
  color: "skyblue",
  border: "none",
  padding: "1rem 2rem"
});

const fontSize = computed(() => `${props.size}px`);
</script>

<template>
  <button :id="id" class="base-button">
    <slot />
  </button>
</template>

<style>
button.base-button {
  padding: v-bind(padding);
  cursor: pointer;
  border: v-bind(border);
  background-color: v-bind(color);
  font-size: v-bind(fontSize);
  color: v-bind(textColor);;
}
</style>