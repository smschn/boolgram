<template>

    <div class="single-post">

        <div class="post-header d-flex jc-sb ai-c">
            <div class="d-flex ai-c">
                <img :src="postP.profile_picture" alt="Profile Picture">
                <span>{{postP.profile_fullname}}</span>
            </div>
            <i class="fa-solid fa-ellipsis"></i>
        </div>

        <img class='post-image' :src="postP.post_image" alt="Post Image">

        <i class="fa-regular fa-heart"></i>
        <i class="fa-regular fa-comment"></i>

        <div class="post-interaction">

            <div class="d-flex ai-c">
                <img :src="postP.likes[0].profile_picture" alt="Profile Picture">
                <span>Piace a&nbsp;</span>
                <span class="bold">{{postP.likes[0].username}}&nbsp;</span>
                <span>e altri&nbsp;</span>
                <span class="bold">{{countLikes(postP.likes)}}</span>
            </div>

            <div class="post-caption">
                <span class="bold">{{postP.profile_name}}&nbsp;</span>
                <span>{{postP.post_text}}</span>
            </div>

            <button @click='showAllCommentsF()'>Mostra tutti i {{countComments(postP.comments)}} commenti</button>
            &nbsp;
            <button v-if='postP.comments.length > 3' @click='showFirstThreeComments()'>Mostra solo i primi 3 commenti</button>
            <div v-for='(comment, index) in showAllComments ? postP.comments : showOnlyFirstThreeComments(postP.comments)'
                :key='index'
                class="post-comment">
                <span class="comment-username">{{comment.username}}</span>
                <span>{{comment.text}}</span>
            </div>

            <div class="post-date">{{truncateDate(postP.date.date)}}</div>                            
        </div>

        <div class="post-add-comment">
            <input type="text" placeholder="Aggiungi un commento">
            <button>Pubblica</button>
        </div>

    </div>

</template>

<script>
export default {
    name: 'SinglePost',
    props: {
        postP: Object,
    },
    data() {
        return {
            showAllComments: false
        }
    },
    methods: {
        truncateDate(dateText) {
            return dateText.substring(0, 19);
        },
        countLikes(likesArray) {
            return likesArray.length-1;
        },
        countComments(commentsArray) {
            return commentsArray.length;
        },
        showOnlyFirstThreeComments(commentsArray) {
            let newCommentsArray = [];
            for (let i = 0; i < 3; i++) {
                newCommentsArray.push(commentsArray[i]);
            }
            return newCommentsArray;
        },
        showAllCommentsF() {
            this.showAllComments = true;
        },
        showFirstThreeComments() {
            this.showAllComments = false;
        }
    }
}
</script>

<style lang='scss' scoped>

    @import '../../../styles/general.scss';
    @import '../../../styles/partials/_singlePost.scss';

</style>