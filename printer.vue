<template>
<div>
  <div v-on:click="print('printableArea')" id="printableArea"> 
 <component :is="printcomponent">
    </component>
    </div>
</div>
</template>

<script>
export default {
  props: ["printcomponent"],
  data: function() {
    return {
      d: this.printcomponent
    };
  },
  methods: {
    print(divName) {
      var printContents = document.getElementById(divName).innerHTML;
      var originalContents = document.body.innerHTML;

      document.body.innerHTML = printContents;

      window.print();

      document.body.innerHTML = originalContents;
    }
  },
  mounted: function() {}
};
</script>

<style scoped>

</style>
