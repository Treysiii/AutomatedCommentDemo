<template>
  <div class="hello-world-box">
    <input v-model="query" placeholder="Filter messages..." />
    <span
      v-for="(msg, i) in filteredMessages"
      :key="i"
      class="hello-world-text"
      :style="{ color: color }"
    >{{ msg }}</span>
    <span v-if="filteredMessages.length === 0" class="no-results">No results found</span>
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
  data() {
    return { query: '' };
  },
  computed: {
    filteredMessages() {
      return this.messages.filter(msg => msg.includes(this.query));
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
.no-results {
  color: gray;
  font-style: italic;
}
</style>
