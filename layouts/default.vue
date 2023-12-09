<template>
  <header>
    <!-- 全局导航栏 -->
    <nav>
      <ul>
        <li>
          <NuxtLink to="/">Home</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/test">Test</NuxtLink>
        </li>
      </ul>

    </nav>
  </header>

  <main class="container">
    <!-- 页面内容 -->
    <slot />
  </main>
</template>

<style>
html,
body {
  padding: 0;
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, Oxygen, Ubuntu,
    Cantarell, Fira Sans, Droid Sans, Helvetica Neue, sans-serif;
  line-height: 1.6;
  font-size: 18px;
}

* {
  box-sizing: border-box;
}

a {
  color: #0070f3;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

img {
  max-width: 100%;
  display: block;
}

main {
  max-width: 36rem;
  padding: 0 1rem;
  margin: 3rem auto ;
}

header ul {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 3rem auto;
  gap: 1rem;
  list-style: none;
}
</style>