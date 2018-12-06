<template>
<div class="main">
  <div class="welcome">
    <img src="../assets/leaflink.png" alt="Leaflink Logo">
    <TopHeading msg="Leaflink" smsg="Making it easier for retailers to order online"/>
  </div>
  <InvoiceBody />
</div>
</template>

<script>
// @ is an alias to /src
import TopHeading from '@/components/TopHeading.vue';
import InvoiceBody from '@/components/InvoiceBody.vue';

export default {
  name: 'main',
  components: {
    TopHeading,
    InvoiceBody,
  },
};
</script>

<style lang="scss" scoped>
.main {
  max-width: 943px;
  .welcome {
    width: 703px;
    display: flex;
    flex-direction: column;
    img {
      width: 329px;
    }
    *:nth-child(2) {
      margin-left: auto;
    }
  }
}
</style>
