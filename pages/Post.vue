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
    
                <b-card img="https://media1.britannica.com/eb-media/20/191120-004-AD2A2694.jpg" title="It's Austria" class="mb-2">
                    I wanna go there
                </b-card>
    
                <div>
                    {{title}}
                </div>
                <br>
                <div>
                    {{content}}
    
                </div>
    
            </div>
    
        </div>
    </section>
</template>

<script>

export default {
    async asyncData({ app }) {
        let posts = (await app.$axios.get('http://www.europeancitiesmarketing.com/wp-json/wp/v2/posts')).data
        return {
            title: posts[1].title.rendered,
            content: posts[1].content.rendered
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
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
}

.subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
}

.links {
    padding-top: 15px;
}
</style>
