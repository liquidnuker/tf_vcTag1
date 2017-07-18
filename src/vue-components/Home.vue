<template>
  <div>

  <component v-bind:is="currentView" />
  <Comp2 />
  <button v-on:click="changeView('Comp1')">change</button>

  </div>
</template>
<script>
import comp1 from "./Comp1.vue";
import comp2 from "./Comp2.vue";

  export default {
    data () {
      return {   
        currentView: comp2
      }
    },
    components: {
      Comp1: comp1,
      Comp2: comp2
    },
    mounted: function () {
      // console.log("Home.vue mounted");
    },
    methods: {
      changeView: function(component) {
        this.currentView = component;
      }
    }
  }
</script>

