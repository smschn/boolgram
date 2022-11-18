<template>

    <main>

        <div v-if='isLoading' id='loader' class="container m-auto">
            <img src="@/assets/pacman.gif" alt="Spinner">
            <h1>In caricamento...</h1>
        </div>

        <div v-else id='main-container' class="container m-auto d-flex jc-sb">

            <!-- inizio parte sinistra -->
            <div class='c-60 m-auto'>

                <!-- inizio storie -->

                <MyStories :storiesP='stories'/>

                <!-- fine storie -->

                <!-- inizio post -->
                <div id='post-container'>

                    <SinglePost v-for='(post, index) in posts' :key='index' :postP='post' />

                </div>
                <!-- fine post -->

            </div>
            <!-- fine parte sinistra -->

            <!-- inizio parte destra -->
            <div class='c-40'>

                <!-- inizio profilo -->
                <div id='profile-right'>
                    <div class="d-flex jc-sb ai-c">
                            <div class="d-flex ai-c">
                                <img src="../../assets/images/profile.jpg" alt="#">
                            </div>
                            <div class="name d-flex ai-c">
                                <p>cancellate_l_ultima_trilogia</p>
                                <p>Luke Skywalker</p>
                            </div>
                            <p  class="c-blue bold">Passa a</p>
                    </div>
                </div>
                <!-- fine profilo -->

                <!-- inizio suggerimenti -->

                <MySuggestions :suggestionsP='stories' />

                <!-- fine suggerimenti -->

                <!-- inizio footer -->
                <div id='footer'>
                     &copy; Copyright 2022
                </div>
                <!-- fine footer -->

            </div>
            <!-- fine parte destra -->

        </div>

    </main>

</template>

<script>

import MyStories from './Left_Side/MyStories.vue';
import SinglePost from './Left_Side/SinglePost.vue';
import MySuggestions from './Right_Side/MySuggestions.vue';

import axios from 'axios'

export default {
    name: 'MyMain',
    components: {
        MyStories,
        SinglePost,
        MySuggestions
    },
    data() {
        return {
            stories: null,
            posts: null,
            isLoading: true
        }
    },
    methods: {
        getStories() {
            axios
            .get( 'https://flynn.boolean.careers/exercises/api/boolgram/profiles' )
            .then( response => {
                this.stories = response.data;
            } )
        },
        getPosts() {
            axios
            .get( 'https://flynn.boolean.careers/exercises/api/boolgram/posts' )
            .then( response => {
                this.posts = response.data;
                this.isLoading = false;
            })
        },
        showLoadingScreen(functionP) {
            setTimeout(functionP, 3000)
        }
    },
    mounted() {
        this.showLoadingScreen(this.getPosts);
        this.showLoadingScreen(this.getStories);
    }
}
</script>

<style lang="scss" scoped>

    @import '../../styles/variables.scss';
    
    main {
        margin-top: 70px;
        padding-top: 50px;
        background-color: $bg2;
    }

    #loader {
        text-align: center;
    }

    /* inizio lato destro */

    /* inizio profilo */
    .c-40 {
        margin-top: 10px;
        padding-left: 30px;
        
        #profile-right {
            margin-bottom: 50px;
            
            img {
                width: 50px;
                border-radius: 50%;
            }

            .name {
                flex-direction: column;

                p:nth-child(2) {
                    color: grey;
                }
            }
        }

        
    }

    /* fine profilo */

    #footer {
        margin-top: 20px;
        color: grey;
        font-size: small;
    }

    /* fine lato destro */

</style>