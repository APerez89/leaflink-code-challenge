<template>
  <div class="sub-total">
    <ul>
      <li>Tax:</li>
      <li>Deduction:</li>
      <li>Sub Total:</li>
    </ul>
    <ul v-for="item in items" :key="item['.key']">
      <li><input v-model="item.tax" type="number" placeholder="%"></li>
      <li><input v-model="item.deduction" type="number" placeholder="$"></li>
      <li>$ {{ total | currency }}</li>
    </ul>
  </div>
</template>

<script>
import items from '@/api/items';

export default {
  name: 'InvoiceSubTotal',
  data() {
    return {
      items,
    };
  },
  computed: {
    total() {
      return this.items.reduce(
        (acc, item) => acc + item.rate * item.quantity * item.tax - item.deduction,
        0,
      );
    },
  },
  filters: {
    currency(value) {
      return value.toFixed(2);
    },
  },
};
</script>

<style lang="scss" scoped>
.sub-total {
  text-align: right;
  display: grid;
  grid-template-columns: 2fr 1fr;
  border-top: 1px solid #eee;
  ul {
    display: grid;
    grid-template-rows: 1fr 1fr 1fr;
    align-items: center;
    margin: 0 25px;
    padding: 0;
    list-style: none;
    li {
      input {
        width: 70%;
        // height: 50px;
        font-family: var(--body-font);
        font-size: var(--body-size-md);
        text-align: center;
        color: #6b6b6b;
        margin: 5px 0;
        padding: 10px;
        &:focus {
          outline-color: var(--blue-dream);
          outline-width: medium;
        }
      }
    }
  }
}
</style>
