<template>
  <h2 class="text" :class="{ active: bek === 'salom' }">
    {{ bek }}
  </h2>
  <slot name="logo"></slot>
  <slot></slot>
  <button @click.self="mClose">
    Modal Close
    <span>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Tempora
      molestiae deleniti nihil distinctio architecto, iste sequi molestias
      exercitationem amet maxime, tempore sint quam, quo harum error totam.
      Provident, quasi libero!
    </span>
  </button>
</template>

<script>
export default {
  props: ["bek"],
  methods: {
    mClose() {
      this.$emit("ochir");
    },
    yoz() {
      console.log("yoz");
    },
  },
};
</script>
<style>
.text {
  color: blue;
}
</style>