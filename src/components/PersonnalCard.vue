<template>
  <div>
    <h3>{{ user.name }}</h3>
    <div class="data"><strong>E-mail:</strong> {{ user.email }}</div>
    <div class="data"><strong>Teléfono:</strong> {{ user.phone }}</div>
    <div class="data"><strong>Ciudad:</strong> {{ user.city }}</div>
    <div class="data"><strong>Idioma:</strong> {{ user.lang }}</div>
    <SocialBar :links="links" />
  </div>
</template>

<script>
import SocialBar from "./SocialBar.vue";

export default {
  name: "PersonnalCard",
  props: ["user", "links"],
  components: {
    SocialBar,
  },
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

.data {
  margin-bottom: 15px;
}
</style>
