<template>
    <div class="tweetGrid">
        <Tweet v-for='tweet in tweets'
        v-bind:key="tweet.content"
        v-bind:author="tweet.author"
        v-bind:content="tweet.content"
        v-bind:class="{ tweetGrid: toggleState }"
        />
  </div>
</template>

<script>
import Tweet from './Tweet.vue'

export default {
    name: "TweetList", 
    components: {
        Tweet
    }, 
    mounted: function(){
        this.$root.$on('toggleView',this.toggleClass);
    },
    methods:{
        toggleClass: function(){
            this.toggleState = true;
            if(!this.toggleState){ // something is wrong here
                this.toggleState = false;
            }
           //change the togglestate to true -- look back a week or so. 
        }
    },
    data: function(){
        return{
            toggleState : false,
            tweets: [
                {
                    author: "Author 1",
                    content:  "you ever just get a sharp stabbing pain in one of your organs and u think ah fuck its finally happening"
                },
                {
                    author: "Author 2",
                    content:  "I need more friends who understand that I still want to be invited but I'm not going"
                },
                {
                    author: "Author 3",
                    content:  "OH SO IM JUST SUPPOSED TO ENJOY GOOD THINGS THAT HAPPEN TO ME INSTEAD OF LIVING IN FEAR THAT THEYLL TURN INTO DUST IN MY HANDS"
                },
                {
                    author: "Author 4",
                    content:  "Sorry im late i sat on my bed in a towel for 45 minutes staring at the wall"
                }
            ]
        }
    }

}
</script>

<style>
.tweetList{
 text-align: center;
}
.tweetGrid{
    display: Grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
}


</style>