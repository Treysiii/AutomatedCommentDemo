<template>
  <div class="hello-world-box">
    <span
      v-for="(msg, i) in messages"
      :key="i"
      class="hello-world-text"
      :style="{ color: color }"
    >{{ msg }}</span>
  </div>
</template>

<script>
export default {
  name: 'HelloWorldBox',
  props: {
    messages: {
      type: Array,
      default: () => ['Hello World', 'Hello World'],
    },
    color: {
      type: String,
      default: 'green',
    },
  },
};
</script>

<style scoped>
.hello-world-text {
  font-size: 30px;
  font-weight: 400;
  display: block;
}
</style>
