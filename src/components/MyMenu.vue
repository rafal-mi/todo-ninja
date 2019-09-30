<template>
  <div class="container">
    <slot name="activator" v-bind:handlers="handlers">
      
    </slot>

  </div>
</template>

<script>
export default {
  name: 'my-menu',
  props: ['handlers']
}
</script>
