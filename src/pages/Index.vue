<template>
  <q-page class="flex flex-center">
    <div class="q-pa-md">
      <div class="row">
        <div class="col">
            <q-dialog no-refocus v-model="showModal">
              <q-card>
                <q-card-section class="row items-center q-pb-none">
                  <div class="text-h6">Close icon</div>
                  <q-space/>
                  <q-btn icon="close" flat round dense v-close-popup/>
                </q-card-section>
                <q-card-section>
                  Lorem Ipsum is simply dummy text of the printing and 
                  typesetting industry. Lorem Ipsum has been the industry's 
                  standard dummy text ever since the 1500s
                </q-card-section>
                <q-card-section>
                  <q-btn color="primary" label="Close dialog" @click="showModal=false" />
                </q-card-section>
              </q-card>
            </q-dialog>
        </div>
      </div>
      <div class="row">
        <div class="col text-center">
          <img src="./../assets/logo-admin.jpg" />
        </div>
      </div>
      <div class="row">
        <div class="col">
          <camera @aprovado="alerta"></camera>
        </div>
      </div>
  </div>
  </q-page>
</template>

<script>
import Camera from 'src/components/Camera.vue'

export default {
  components: { Camera },
  name: 'PageIndex',
  data: function() {
    return {
      showModal: false,
    }
  },
  methods: {
    alerta: function () {
      console.log('a');
      this.showModal = true;
    },
  }
}
</script>
