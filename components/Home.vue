<template>
  <div  >
    <div class="flex items-start justify-center text-white  p-4 h-screen" >
        <div class="grid gap-4 grid-cols-1 w-full"  >
            <p class="text-center h-16 text-2xl"  >Removedor de Background</p>
            <InputFile @file-updated="atualizarArquivo" class="h-16"   />
            <p v-if="imagem!=null">{{imagem.name}} - <span class="text-green-400"> {{imagem.size}} Bytes</span></p>
            <div class="flex justify-center border rounded-lg border-blue-500" v-if="imagem!=null" >
                <img :src="url" alt="Image"  style="height: 23rem;" v-if="imagem!=null">
            </div>
            <ButtonForm v-if="imagem!=null" @click="removerBg"/>
        </div>
    </div>
  </div>
</template>

<script>
import ButtonForm from './Ui/ButtonForm.vue'
import InputFile from './Ui/InputFile.vue'

export default {
    name: 'Home',
    data() {
        return {
            imagem: null,
            url: null,
        }
    },
    components: {
        InputFile,
        ButtonForm,
    },
    methods: {
        atualizarArquivo(e) {
            this.url = URL.createObjectURL(e);
            this.imagem = e;
            console.log(this.imagem)
        },
        async removerBg() {
            const data = new FormData();
            data.append("file", this.imagem);

            const options = {
                method: 'POST',
                headers: {
                    'X-RapidAPI-Key': 'd0146d5790msh6ba282319190f7cp1e8e7cjsn56997398e517',
                    'X-RapidAPI-Host': 'remove-bground.p.rapidapi.com'
                },
                body: data
            };
            let dados;
            fetch('https://remove-bground.p.rapidapi.com/', options)
                .then(response =>  {
                    response.blob().then( responseBlob => {
                        this.url = URL.createObjectURL(responseBlob)
                    })                
                })
                .catch(err => console.error(err));
                }
    },

}
</script>

<style>

</style>