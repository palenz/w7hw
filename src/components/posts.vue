<template>

<div class=image-container>
    
        <div v-for='(post, index) in subData.data.children' v-if="post.data.is_reddit_media_domain" :post='post' :key="index">
            <img :src="post.data.url_overridden_by_dest" height='450' class="image" :key="index">
            <p>{{post.data.title}}</p> 
        </div>


    </ul>
</div>

</template>

<script>
export default {
    name: 'posts',
    props: ['subData']
};
</script>

<style>


</style>