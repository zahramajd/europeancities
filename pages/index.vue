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
          this is the main page of my blog, your ip is {{ip}}
        </div>
      </div>
  
    </div>
  </section>
</template>

<script>

export default {
  async asyncData({ app }) {
    const { data } = await app.$axios.get('http://icanhazip.com')
    return {
      ip: data
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
</style>
