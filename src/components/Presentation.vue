<template>
  <div class="paragraph">
    <h3>{{ content.metadata.pres_title }}</h3>
    <p>{{ content.metadata.pres_first }}</p>
    <p>{{ content.metadata.pres_second }}</p>
    <p>{{ content.metadata.pres_three }}</p>
  </div>
</template>

<script>
export default {
  name: "Description",
  props: ["content"],
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

.paragraph {
  color: map-get($colors, primary);
  .begin {
    color: map-get($colors, secondary);
  }
}
</style>
