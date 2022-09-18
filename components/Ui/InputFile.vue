<template>
  <div class="flex w-full" > 
    <label class="block w-full mb-2 px-2 py-3 text-lg text-center bg-gray-400 font-medium text-gray-900 rounded-lg dark:text-white hover:bg-gray-500 hover:text-white" for="file_input"
    
    >
        <font-awesome-icon :icon="['fas', 'upload']"></font-awesome-icon>
        Escolher Imagem
    </label>
    <input class="block" aria-describedby="file_input_help"
    accept="image/*"
     id="file_input"
      type="file" 
     @change="onFileChange"
     >
  </div>
</template>

<script>
export default {
    name: 'InputFile',
        methods: {
        onFileChange(e) {
            const file = e.target.files[0];
            if(file) {
                this.$emit('file-updated', file);
            }
        }
    },
}
</script>

<style scoped>
input[type="file"] {
    display: none;
}

label {

}
</style>