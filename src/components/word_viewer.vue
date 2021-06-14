<template>
    <div>
        <VueDocPreview :value="file_content_word" type="office" />
    </div>
</template>

<script>
import VueDocPreview from 'vue-doc-preview'

export default {
    name: 'word_viewer',

    components: { VueDocPreview },

    props: ['file_content_word']
}
</script>

<style scoped>

</style>