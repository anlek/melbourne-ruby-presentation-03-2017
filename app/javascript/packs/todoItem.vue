<template>
  <li class="list-group-item">
    <label class="form-check-label">
      <input class="form-check-input" type="checkbox" value="" v-model="item.checked">
      {{ item.name }}
    </label>
  </li>
</template>

<script>
  export default {
    props: {
      item: {
        type: Object, // String, Number, Boolean, Function, Object, Array
        required: true
      }
    }
  }
</script>

<style scoped>
  .done {
    text-decoration: line-through;
    font-weight: 400;
  }
</style>
