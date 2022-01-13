<template>
  <div>
    <h2>Material Color</h2>
    <v-color-picker
      dot-size="25"
      mode="hexa"
      v-model="color"
      hide-canvas
      swatches-max-height="200"
    ></v-color-picker>
  </div>
</template>

<script>
export default {
  data: () => ({ color: null }),
  watch: {
    color() {
      if (this.color.hex) {
        this.$store.state.color = this.color.hex;
      }
    },
  },
};
</script>

<style>
</style>