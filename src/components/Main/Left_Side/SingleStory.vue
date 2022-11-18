<template>

        <div class="single-story d-flex">

            <img :src="storyP.profile_picture" alt="Profile Image">
            
            <p>{{truncateProfileName(storyP.profile_name)}}</p>

        </div>

</template>

<script>
export default {
    name: 'SingleStory',
    props: {
        storyP: Object
    },
    methods: {
        truncateProfileName(text) {
            if (text.length > 8) {
                return text.substring(0, 8) + '...';
            } else {
                return text;
            }
        }
    }
}
</script>

<style lang='scss' scoped>

    @import '../../../styles/partials/_singleStory.scss';

</style>