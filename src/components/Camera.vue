<template>
<div>
    <div class="row q-mt-xl">
      <div class="col text-center">
        <qrcode-stream @decode="onDecode"></qrcode-stream>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <q-item clickable v-ripple class="bg-grey-2">
          <q-item-section>
            <q-item-label>
              Texto Lido: 
            </q-item-label>
            <q-item-label caption>
              {{texto_lido}}
            </q-item-label>
          </q-item-section>
        </q-item>
      </div>
    </div>
</div>
</template>

<script>
import { QrcodeStream } from 'vue-qrcode-reader'
import { Loading, QSpinnerGrid } from 'quasar'
export default {
  name: 'Camera',
  components: {
    QrcodeStream,
    Loading,
  },
  data: function (){
    return {
      decodedString: '',
      texto_lido: ''
    }
  },
  watch: {
    texto_lido: function(value) {
      console.log(value);
      this.buscarRegistro();
    } 
  },
  methods: {
    onDecode: function (decodedString) {
        this.texto_lido = decodedString;
    },
    buscarRegistro: function() {
      Loading.show({
        spinner: QSpinnerGrid,
      });
      setInterval(() => {
        Loading.hide();
        this.$emit('aprovado');
      }, 5000);
    },
  }
}
</script>
