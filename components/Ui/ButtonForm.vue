<template>
  <button
  @click="$emit('click')"
   class="bg-blue-500 hover:bg-blue-700 text-white font-bold px-2 py-3 rounded">
    Remover Background
  </button>
</template>

<script>
export default {
    name: 'ButtonForm' ,
}
</script>

<style>

</style>