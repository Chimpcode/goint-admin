<style lang="css">



</style>

<template lang="html">

    <infobar name="Vivanda" :plan="0" :data="filler"></infobar>

</template>

<script>
import Infobar from '~/components/infobar'
export default {
    components: {
        Infobar
    },
    data: () => {
        return {
            filler: [
                {count: 10, type: 'Post creados'},
                {count: 21, type: 'Usuarios siguiendolo'},
                {count: 102, type: 'Ventas concretadas'}
            ]
        }
    }
}
</script>
