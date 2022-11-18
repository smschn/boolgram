<template>

    <div id='stories-container' class="d-flex">

        <SingleStory v-for="(story, index) in storiesP" :key='index' :storyP='story' />

    </div>

</template>

<script>

import SingleStory from './SingleStory.vue';

export default {
    name: 'MyStories',
    components: {
        SingleStory
    },
    props: {
        storiesP: Array
    }
}
</script>

<style lang='scss' scoped>

    @import '../../../styles/partials/_myStories.scss';

</style>