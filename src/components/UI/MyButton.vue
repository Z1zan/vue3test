<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
  .btn {
    margin-top: 15px;
    padding: 10px 15px;
    background: none;
    color: teal;
    cursor: pointer;
    border: 1px solid teal;
    border-radius: 4px;
    align-self: flex-end;
  }
</style> 