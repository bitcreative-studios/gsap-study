<template>
  <header class="flex justify-between items-center p-12 text-white">
    <div class="uppercase tracking-widest text-2xl">
      some edition
    </div>
    <nav class="nav">
      <ul class="flex items-center space-x-16">
        <li class="h-2 w-2 rounded-full bg-white">
          <a class="opacity-0" href="#">artworks</a>
        </li>
        <li><a href="#">studio</a></li>
        <li><a href="#">where</a></li>
        <li><a href="#">code</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style scoped></style>
