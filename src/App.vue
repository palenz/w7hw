<template>

<posts :subData="subData" v-if="subreddit"></posts>

</template>

<script>

import posts from './components/posts.vue'
 
export default {
  name: 'App',
  data (){
    return {
      subData: null,
      subreddit: null
    };
  },

  mounted(){
    fetch('https://www.reddit.com/r/$(subreddit).json?limit=30')
    .then(res => res.json())
    .then(subData => this.subData = subData)
  },

  components: {
    'posts': posts
  }
}
</script>

<style>
.image-container{
    font-family: avenir;
    flex-wrap: wrap;
    padding: 5px;
    align-sel: center
};

.image{
  align-content: center;
}

.image-container > div{
  padding: 5px;
  align-content: center;
}

.overlay-slide {
	position: relative;
    box-sizing: border-box;
    overflow: hidden;
    float: left;
    margin: 10px;
}

.overlay-slide:hover div {
    transform: translate(0, 0);
	transition: 0.8s;
}
.overlay-slide div {
	position: absolute;
    box-sizing: border-box;
    bottom: 0;
    transform: translate(0, 100%);
    padding: 15px;
    background-color: rgba(0,0,0,0.5);
    text-align:center;
    transition: 0.3s;

}
.overlay-slide p {
    font-size: 14px;
    color: #dddddd;
}


</style>