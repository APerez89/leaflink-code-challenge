<template>
  <div class="invoice-items">
    <div class="top-bar">
      <ul>
        <li>Item Description</li>
        <li>Quantity</li>
        <li>Rate</li>
        <li>Total</li>
      </ul>
    </div>
    <div class="items">
      <ul v-for="item in items" :key="item['.key']">
        <li><input v-model="item.description" placeholder="Item Description"></li>
        <li><input type="number" v-model="item.quantity" placeholder="0"></li>
        <li>$ <input type="number" v-model="item.rate" placeholder="0"></li>
        <li>${{ item.quantity * item.rate | currency }}</li>
      </ul>
    </div>
    <div class="bottom-bar">
      <InvoiceButton />
      <InvoiceSubTotal />
    </div>
  </div>
</template>

<script>
import items from '@/api/items';
import InvoiceButton from '@/components/InvoiceButton.vue';
import InvoiceSubTotal from '@/components/InvoiceSubTotal.vue';

export default {
  name: 'InvoiceItems',
  components: {
    InvoiceButton,
    InvoiceSubTotal,
  },
  data() {
    return {
      items,
    };
  },
  filters: {
    currency(value) {
      return value.toFixed(2);
    },
  },
};
</script>

<style lang="scss" scoped>
.invoice-items {
  font-family: var(--body-font);
  font-size: var(--body-size-bg);
  .top-bar {
    width: 100%;
    height: 50px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    color: #afafaf;
    border-bottom: 1px solid #eee;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
    ul {
      list-style: none;
      padding: 0 25px;
      display: grid;
      grid-template-columns: 3fr 1fr 1fr 2fr;
      *:nth-child(2), *:nth-child(3) {
        text-align: center;
      }
      *:nth-child(4) {
        text-align: right;
      }
    }
  }
  .items {
    // margin: 25px 0;
    ul {
      list-style: none;
      margin: 0 0 25px;
      padding: 25px;
      display: grid;
      grid-template-columns: 3fr 1fr 1fr 2fr;
      border-bottom: 1px solid #eee;
      li {
        input {
          width: 75%;
          // height: 50px;
          font-family: var(--body-font);
          font-size: var(--body-size-md);
          color: #6b6b6b;
          padding: 10px;
          &:focus {
            outline-color: var(--blue-dream);
            outline-width: medium;
          }
        }
      }
      *:nth-child(4) {
        display: flex;
        flex-direction: column;
        justify-content: center;
        text-align: right;
        color: var(--blue-dream);
      }
    }
  }
  .bottom-bar {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
