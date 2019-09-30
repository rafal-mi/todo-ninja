<template>
<span>
  <slot v-bind:user="user">{{ user.lastName }}</slot>
</span>
</template>

<script>
export default {
    name: 'CurrentUser',
    props: ['user']
}
</script>
