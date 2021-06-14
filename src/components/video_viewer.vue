<template>
    <div>
        <div class="player-container">
            <vue-core-video-player :src="file_content_video"></vue-core-video-player>
        </div>
    </div>
</template>

<script>
export default {
    name: 'video_viewer',

    props: ['file_content_video']
}
</script>

<style scoped>

</style>