<template>
    <div>
        <VueDocPreview :value="file_content_powerpoint" type="office" />
    </div>
</template>

<script>
import VueDocPreview from 'vue-doc-preview'

export default {
    name: 'powerpoint_viewer',

    components: { VueDocPreview },

    props: ['file_content_powerpoint']
}
</script>

<style scoped>

</style>