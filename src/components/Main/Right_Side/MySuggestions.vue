<template>

    <div id='suggestions'>

        <div class="d-flex jc-sb">
            <div class="suggestions-for-you">Suggerimenti per te</div>
            <div class="bold">Mostra tutti</div>
        </div>

        <ul>
            <li v-for='(suggestion, index) in suggestionsP' :key='index' class="suggestion-item d-flex jc-sb ai-c">
                <div>
                    <div class="d-flex jc-sb ai-c">
                        <img :src="suggestion.profile_picture" alt="Profile Picture">
                        <span>{{suggestion.profile_name}}</span>
                    </div>
                </div>
                <p class="c-blue bold">Segui</p>
            </li>
        </ul>

    </div>

</template>

<script>
export default {
    name: 'MySuggestions',
    props: {
        suggestionsP: Array
    }
}
</script>

<style lang='scss' scoped>

    @import '../../../styles/partials/_mySuggestions.scss';
    @import '../../../styles//variables.scss';
    @import '../../../styles//general.scss';
    
</style>