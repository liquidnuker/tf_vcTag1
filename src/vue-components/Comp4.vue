<template>
  <div>
    Comp4.vue
    <br>
    url: {{ prUrl }}
    <br>
    {{ prMessage }} 
  </div>
</template>
<script>
export default {
    data () {
      return {   
        
      }
    },
    props: [
      'prMessage',
      'prUrl'
    ],
    components: {
     
    },
    mounted: function () {
      
    },
    methods: {
      
    }
  }
</script>