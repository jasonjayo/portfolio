<template>
  <RouterView />
  <footer>
    <div>&copy; Jason Gill {{ new Date().getFullYear() }}</div>
    <div>
      <a target="_blank" href="https://github.com/jasonjayo/portfolio"
        >Website source code</a
      >
    </div>
  </footer>
</template>

<style lang="scss">
footer {
  background: #00294d;
  margin-top: 8em;
  color: #00294d;
  color: #fff;
  text-align: center;
  padding: 3em;
  display: flex;
  flex-wrap: wrap;
  gap: 3em;
  justify-content: center;
  a {
    color: inherit;
  }
}
</style>
