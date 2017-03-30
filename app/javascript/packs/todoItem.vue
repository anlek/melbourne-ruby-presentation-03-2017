<template>
  <li class="list-group-item">
    <label :class="{ 'form-check-label': true, 'done': item.checked }">
      <input class="form-check-input" type="checkbox" value="" v-model="item.checked">
      {{ item.name }}
    </label>
    <a @click="remove" class="remove">x</a>
  </li>
</template>

<script>
  export default {
    props: {
      item: {
        type: Object, // String, Number, Boolean, Function, Object, Array
        required: true
      }
    },
    methods: {
      remove () {
        this.$emit("delete", this.item)
      }
    }
  }
</script>

<style scoped>
  .done {
    text-decoration: line-through;
    font-weight: 400;
  }
  .remove {
    float: right;
    padding: 3px 5px;
    cursor: pointer;
    border-radius: 4px;
    transition: all 300ms;
    color: pink;
    font-weight: 900;
  }
  .remove:hover {
    color: red;
    text-decoration: none;
  }
</style>
