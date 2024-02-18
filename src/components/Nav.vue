<script></script>

<template>
  <nav>
    <ul>
      <li><a href="#post1">Post1</a></li>
      <li><a href="#post2">Post2</a></li>
      <li><a href="#post3">Post3</a></li>
      <li><a href="#post4">Post4</a></li>
    </ul>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
}

ul {
  display: flex;
  list-style: none;
  gap: 30px;
  font-size: 24px;
}

a {
  color: white;
  text-decoration: underline;
  font-family: cursive;
  font-style: italic;
  font-weight: 700;
}

a:hover {
  cursor: pointer;
  outline: none;
  color:aqua
}
</style>
