<template>
    <div id="content">
    <my-menu>
        <template v-slot:activator="{ on }">
            
            <v-btn v-on="on">Button</v-btn>
        </template>

    </my-menu>
    </div>
</template>

<script>
import MyMenu from './MyMenu'

export default {
    components: { MyMenu }
    
}
</script>