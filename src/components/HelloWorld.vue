<template>
  <h3 v-bind="$attrs">Hello From Component</h3>
  <h5>Received name: {{ props.name }}</h5>
  <button @click="getAlert">Press Me</button>
</template>

<script lang="ts">
export default {
  inheritAttrs: false
};
</script>

<script lang="ts" setup>
// import { useAttrs } from "vue";

// const attrs = useAttrs();
// console.log(attrs);

const emits = defineEmits(["pressed"]);

function getAlert() {
  emits("pressed");
}

interface props {
  name?: string;
}
const props = withDefaults(defineProps<props>(), {
  name: "Stewart"
});
</script>

<style>
.green {
  background-color: green;
}
</style>
