<template>
  <div class="container">
    <p>MyMenu: The 'handlers' object is {{ handlers }} </p>
    <slot name="activator" v-bind:handlers="handlers"></slot>
  </div>
</template>

<script>
export default {
  name: "my-menu",
  props: {
    handlers: {
      type: Object,
      default: () => {}
    }
  }
};
</script>
