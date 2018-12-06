<template>
  <div class="invoice-button">
    <button class="btn" @click="addItem">Add Item</button>
  </div>
</template>

<script>
import items from '@/api/items';

export default {
  name: 'InvoiceButton',
  data() {
    return {
      items,
    };
  },
  methods: {
    addItem() {
      this.items.push({ description: '', quantity: [], rate: [] });
    },
  },
};
</script>

<style lang="scss" scoped>
.btn {
  margin: 25px;
  padding: 8px 25px;
  background-color: var(--blue-dream);
  color: var(--white-widow);
  font-size: var(--body-size-bg);
  border: none;
  border-radius: 2px;
  cursor: pointer;
  transition: all 0.2s;
  &:hover {
    transform: scale(1.1);
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
  }
  &:focus {
    outline: none;
  }
}
</style>
