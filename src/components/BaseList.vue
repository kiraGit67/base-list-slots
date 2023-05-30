<template>
  <slot name="header">
    <h2>{{ headline }}</h2>
  </slot>
  <div class="intro-text"><slot /></div>
  <ul>
    <li v-for="item in listItems" :key="item.id">{{ item.text }}</li>
  </ul>
</template>

<script>
const timestamp = +new Date();
export default {
  props: {
    headline: String,
    listItems: {
      type: Array,
      default: () => [{ text: "No items exist yet", id: timestamp }],
    },
  },
};
</script>
