<template>
<div>
  <div v-on:click="print('printableArea')"> 
 <component :is="printcomponent">
    </component>
    </div>
</div>
</template>

<script>
export default {
  props: ["printcomponent", "printer_off"],
  data: function() {
    return {};
  },
  watch: {
    printer_off: function() {
      var self = this;

      if(self.printer_off != true){
      window.print();
      self.$emit("printerStatus", true);
      }
    }
  },
  methods: {
    print() {
      var self = this;
      self.$emit("printerStatus", false);
    }
  },
  mounted: function() {}
};
</script>

<style scoped>

</style>
