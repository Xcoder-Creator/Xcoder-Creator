<template>
    <div>
        <VueDocPreview :value="file_content_excel" type="office" />
    </div>
</template>

<script>
import VueDocPreview from 'vue-doc-preview'

export default {
    name: 'excel_viewer',

    components: { VueDocPreview },

    props: ['file_content_excel']
}
</script>

<style scoped>

</style>