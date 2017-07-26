<template>
    <section class="container">
        <div>
    
            <div>
                <b-button-group>
                    <b-button active>
                        <router-link to="/index">main</router-link>
                    </b-button>
                    <b-button>
                        <router-link to="/post">post</router-link>
                    </b-button>
                    <b-button>
                        <router-link to="/category">category</router-link>
                    </b-button>
                </b-button-group>
    
                <br>
                <br>
    
            </div>
    
            <div class="title" v-html="post.title.rendered"></div>
            <div v-html="post.content.rendered"></div>
    
        </div>
    </section>
</template>

<script>

export default {

    async asyncData({ params, app }) {
        let post = (await app.$axios.get('http://www.europeancitiesmarketing.com/wp-json/wp/v2/posts/' + params.id)).data
        return {
            post: post
        }
    }
}

</script>

<style>
.container {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.title {
    font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    /* 1 */
    display: block;
    font-weight: 200;
    font-size: 30px;
    color: #35495e;
    letter-spacing: 1px;
}
</style>
