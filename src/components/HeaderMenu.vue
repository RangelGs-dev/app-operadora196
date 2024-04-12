<template>
  <div class="header">
    <div class="logo">
      <img alt="Vue logo" src="../assets/logo.png" />
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
        { href: "/about", label: "Sobre" },
        { href: "/contact", label: "Contato" },
      ],
    };
  },
};
</script>

<style scoped>
.header {
  background-color: #f0f0f0;
  padding: 20px;
}

.logo {
  float: left;
}

.logo img {
  height: 50px;
}

nav {
  float: right;
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

nav li {
  display: inline-block;
  margin-right: 20px;
}

nav a {
  text-decoration: none;
  color: #333;
}
</style>
