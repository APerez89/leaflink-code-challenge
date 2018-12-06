<template>
  <div class="heading">
    <h1>{{ msg }}</h1>
    <h2>{{ smsg }}</h2>
  </div>
</template>

<script>
export default {
  name: 'TopHeading',
  props: {
    msg: String,
    smsg: String,
  },
};
</script>

<style lang="scss" scoped>
.heading {
  width: 460px;
  text-align: center;
}
</style>
