<template>
  <nav id="nav">
    <p class="logo">My Travel App</p>
    <ul class="nav-links">
      <li class="links"><router-link to="/">Home</router-link></li>
      <li
        class="links"
        v-for="destination in destinations"
        :key="destination.name"
      >
        <router-link
          :to="{
            name: 'DestinationDetails',
            params: { slug: destination.slug }
          }"
        >
          {{ destination.name }}
        </router-link>
      </li>
    </ul>
  </nav>
</template>

<script>
import store from "@/store";
export default {
  data() {
    return {
      destinations: store.destinations
    };
  }
};
</script>

<style scoped>
#nav {
  display: flex;
  justify-content: center;
  padding: 30px;
}
.nav-links {
  display: flex;
}
.links {
  list-style: none;
  padding-right: 20px;
}
#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding: 0 20px;
}
#nav a.my-active-link {
  color: purple;
}
.logo {
  font-size: 20px;
  color: purple;
  font-weight: bold;
}
a:visited {
  text-decoration: underline;
}
</style>
