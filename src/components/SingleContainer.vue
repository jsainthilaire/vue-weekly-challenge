<template>
  <section class="row">
    <button @click="addLiquid">+ {{ containerName }}</button>
    <div class="container" :style="{ marginBottom: containerDistanceToBottom }">
      <div class="liquid" :style="{ height: waterLevel + '%' }"></div>
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
      },
      distanceToBottom: {
        type: Number,
        default: 0,
      }
    },
    methods: {
      addLiquid: function () {
        this.$emit('addLiquid', { containerName: this.containerName })
      }
    },
    computed: {
      containerDistanceToBottom: function () {
        return this.distanceToBottom * -1 * 20 + 'px';
      }
    }
  }
</script>

<style scoped>
  .container {
    border: solid;
    border-top: none;
    display: flex;
    flex-direction: column-reverse;
    width: 40px;
    height: 100px;
    background-color: #eee;
    margin-top: 20px;
    transition: width 500ms;
  }
</style>