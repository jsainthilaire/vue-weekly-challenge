<template>
  <div>
    <SingleContainer
        :waterLevel="containerALvl"
        container-name="A"
        v-on:addLiquid="addLiquidToContainer">
    </SingleContainer>
    <SingleContainer
        :waterLevel="containerBLvl"
        container-name="B"
        v-on:addLiquid="addLiquidToContainer">
    </SingleContainer>
  </div>
</template>

<script>
  import SingleContainer from './SingleContainer.vue'

  const stepLenght = 20
  const nameTovalueMap = {
    A: 'containerALvl',
    B: 'containerBLvl',
  }


  export default {
    name: 'Containers',
    data: function () {
      return {
        containerALvl: 20,
        containerBLvl: 20,
      }
    },
    methods: {
      addLiquidToContainer: function (payload) {
        const { containerName } = payload
        const containerValue = nameTovalueMap[containerName]

        this[containerValue] += stepLenght;
      }
    },
    components: {
      SingleContainer,
    }
  }
</script>
