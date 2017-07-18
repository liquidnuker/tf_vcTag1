<template>
  <div>
    Comp1.vue
    <div id="mount">
    </div>
  </div>
</template>
<script>
  export default {
    data () {
      return {   
        
      }
    },
    components: {
    },
    mounted: function () {
      console.log("comp1 mounted");
      this.loadz();
    },
    methods: {
      loadz: function() {
        console.log("comp1 load");
        const Comp3 = resolve => {
          require.ensure(['./Comp3.vue'], () => {
            resolve(require('./Comp3.vue'))
          })
        };
        new Vue({
          el: '#mount',
          render: h => h(Comp3)
        })
      }
    }
  }
</script>