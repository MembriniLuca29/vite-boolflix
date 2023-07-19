<script>
import headerComponent from './components/headerComponent.vue';
import mainComponent from './components/mainComponent.vue';
import footerComponent from './components/footerComponent.vue';

export default {
  name: "app",
  components: {
    headerComponent,
    mainComponent,
    footerComponent,
  },
};
</script>

<template>
  <headerComponent/>

  <mainComponent/>

  <footerComponent/>

</template>

<style lang="scss" scoped>
$brand_primary: green;

h1{
  color: $brand_primary;
}
</style>
