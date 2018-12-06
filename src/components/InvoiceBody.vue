<template>
  <div class="invoice">
    <InvoiceItems />
  </div>
</template>

<script>
import InvoiceItems from '@/components/InvoiceItems.vue';

export default {
  name: 'InvoiceBody',
  components: {
    InvoiceItems,
  },
};
</script>

<style lang="scss" scoped>
.invoice {
  max-width: 943px;
  height: 780px;
  background-color: #ffffff;
  margin: 91px 0;
  overflow: scroll;
}
</style>
