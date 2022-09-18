<template>
  <div class="p-10" >
    <div class="flex justify-center text-white border rounded-md" style="border:1px solid red;">
        <div class="grid gap-4 grid-cols-1">
            <p>Removedor de Background</p>
            <input type="file" name="imageUpload" id="">
            <InputFile/>
        </div>
    </div>
  </div>
</template>

<script>
import InputFile from './Ui/InputFile.vue'
export default {
    name: 'Home',
    components: {
        InputFile,
    }
}
</script>

<style>

</style>