<template>
  <section class="row">
    <button @click="addLiquid">+ {{ containerName }}</button>
    <div class="container">
      <div class="liquid" :style="{ height: waterLevel + '%' }"></div>
    </div>
    <div class="percentage">
      {{ Math.round(waterLevel) + '%' }}
    </div>
  </section>
</template>

<script>
  export default {
    name: "SingleContainer",
    props: {
      waterLevel: {
        type: Number,
        default: 0,
      },
      containerName: {
        type: String,
        required: true,
      }
    },
    methods: {
      addLiquid: function () {
        this.$emit('addLiquid', { containerName: this.containerName })
      }
    }
  }
</script>

<style scoped>
  .container {
    display: flex;
    flex-direction: column-reverse;
    width: 40px;
    height: 100px;
    background-color: #eee;
    margin-top: 20px;
    transition: width 500ms;
  }

  .liquid {
    display: flex;
    flex-direction: column-reverse;
    width: 40px;
    height: 100px;
    background-color: blue;
    transition: width 500ms;
  }
</style>