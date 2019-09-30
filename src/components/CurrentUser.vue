<template>
<span>
  <slot v-bind:user="user">{{ user.lastName }}</slot>
</span>
<!-- <div>
  Last name: {{user.lastName}}
</div> -->
</template>

<script>
export default {
    name: 'CurrentUser',
    props: ['user']
}
</script>
