<template>
  <div class="home">
    <h1>All destinations</h1>
    <div class="destinations">
    <div v-for="destination in destinations" :key="destination.name">
       <!-- here name shoud be the same name give to the route in routes.js -->
      <router-link :to="{name: 'destinationDetails', params: {slug: destination.slug}}">
        <h2>{{ destination.name }}</h2>
      </router-link>
      <figure>
        <!-- here name shoud be the same name give to the route in routes.js -->
        <router-link :to="{name: 'destinationDetails', params: {slug: destination.slug}}">
          <img :src="require(`@/assets/${destination.image}`)" 
          :alt="destination.name">
        </router-link>
      </figure>
    </div>
    </div>
  </div> 
</template>

<script>
// @ is an alias to /src
import store from "@/store.js"


export default {
  name: "Home",
  components: { },
      data(){
        return{
            destinations:store.destinations
        }
    }
};
</script>
<style scoped>
  .home{
    max-width: 1200px;
    margin: 0 auto;;
  }
  img{
    max-width: 200px;
  }
  .destinations{
    display: flex;
    justify-content: space-between;
  }
  a{
    color: lightseagreen;
    text-decoration: none;
  }
  a:hover, a:visited{
    text-decoration: underline;
  }
</style>
