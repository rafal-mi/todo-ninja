<template>
  <div id="content">
    <base-layout>
      <template v-slot:header>
        <h1>Here might be a page title</h1>
      </template>

      <p>A paragraph for the main content.</p>
      <p>And another one.</p>

      <template v-slot:footer>
        <p>Here's some contact info</p>
      </template>
    </base-layout>
    <current-user></current-user>
    <br/>
    <current-user></current-user>
    <current-user>
      <template v-slot:default="slotProps">
        {{ slotProps.user.firstName }}
      </template>
    </current-user>
  </div>
</template>

<script>
import BaseLayout from "./BaseLayout";
import CurrentUser from "./CurrentUser";

export default {
  name: 'use-slots',
  components: { BaseLayout, CurrentUser },
  data() {
    return {
      slotProps: {
        user: {
          firstName: 'Anna',
          lastName: 'Nyrek'
        }
      }
    }
  }
};
</script>
