<template>
    <div id="content">
    <my-menu :handlers="{ on }">
        <template v-slot:activator="{ on }">
            <p>MyMenuUse: The 'on' object is {{ on }}</p>
            <v-btn v-on="on">Button</v-btn>
        </template>

    </my-menu>
    </div>
</template>

<script>
import MyMenu from './MyMenu'

export default {
    components: { MyMenu },
    data() {
        return {
            on: {click: () => console.log('Clicked')}
        }
    }
}
</script>