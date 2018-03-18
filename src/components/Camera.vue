 <template>
   <div>
     <template v-for="container in containers">
       <button :class="{selected: showContainer === container}" @click="toggleCam(container)">CAM {{ container }}</button>
     </template>
   </div>
 </template>

<script>
  import { EventBus, TOGGLE_CAM } from './EventBus';

  export default {
    name: "Camera",
    props: {
      containers: {
        type: Array,
        default: function () {
          return ['A', 'B']
        },
      },
    },
    data: function () {
      return {
        showContainer: '',
      }
    },
    methods: {
      toggleCam(containerName = '') {
        this.showContainer = containerName === this.showContainer ? '' : containerName;
        EventBus.$emit(TOGGLE_CAM, this.showContainer)
      }
    }
  }
</script>

<style>
  .selected {
    background-color: grey;
    color: white;
  }
</style>