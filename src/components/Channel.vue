<template>
  <section class="row channel-container">
    <div class="channel" :style="{ marginBottom: getPosition + 'px' }">
      <div class="liquid-container">
        <div :class="classes" :style="{ height: level + 'px'}">
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  export default {
    name: "Channel",
    props: {
      channelPosition: {
        type: Number,
        default: 0,
      },
      level: {
        type: Number,
        default: 0,
      }
    },
    computed: {
      getPosition: function () {
        return this.channelPosition * 20;
      },
      classes: function () {
        return {
          liquid: true,
          empty: this.level === 0,
        }
      }
    }
  }
</script>

<style scoped>
  .channel-container {
    z-index: 2;
  }
  .channel {
    border: solid;
    border-left: none;
    border-right: none;
    margin-left: -5px;
    border-radius: 8px;
    margin-right: -5px;
    transition: width 500ms;
  }

  .channel .empty {
    background-color: #eee;
  }

  .channel .liquid {
    width: 50px;
  }

  .liquid-container {
    align-items: flex-end;
    display: flex;
    min-height: 20px;
    background-color: #eee;
  }
</style>