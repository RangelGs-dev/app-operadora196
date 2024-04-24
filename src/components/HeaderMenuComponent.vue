<template>
  <div class="header">
    <div class="logo">
      <img alt="Vue logo" src="../assets/layout_set_logo.png" />
    </div>
    <nav>
      <ul>
        <li v-for="link in links" :key="link.href">
          <a :href="link.href">{{ link.label }}</a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        { href: "/", label: "Home" },
        { href: "article", label: "Artigo" },
        { href: "/feed", label: "Feed" },
        { href: "/about", label: "Sobre" },
      ],
    };
  },
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  background-color: #f0f0f0;
  padding: 20px;
  font-family: "Inter var experimental", "Inter var", Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
}

.logo img {
  max-width: 150px;
  max-height: 65px;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav ul {
  display: inline-block;
  list-style: none;
  margin: 0;
  padding: 0;
}

nav li {
  display: inline-block;
  margin-right: 20px;
}

nav a {
  font-weight: bold;
  text-decoration: none;
  color: #808080;
}
</style>
