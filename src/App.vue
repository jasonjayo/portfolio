<template>
  <RouterView />
  <footer>
    <div>&copy; Jason Gill {{ new Date().getFullYear() }}</div>
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
  gap: 3em;
  justify-content: center;
}
</style>
