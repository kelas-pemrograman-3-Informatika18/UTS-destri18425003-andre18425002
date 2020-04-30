<template>
    <q-page padding>
        <q-card flat >
            <q-card-section class="q-gutter-md">
                <div class="text-h5">Input Jadwal</div>
                <q-form
                @submit="onSubmit"
                @reset="onReset"
                class="q-mt-lg"
                >
                    <div class="q-gutter-md">
                        <q-input label="Waktu" v-model="waktu" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Waktu']"></q-input>
                        <q-input label="Tujuan" v-model="tujuan" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Tujuan']"></q-input>
                        <q-input label="Harga" v-model="harga" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Harga']"></q-input>
                        <q-btn type="submit" label="Input" color="grey" unelevated></q-btn>
                        <q-btn type="reset" label="Reset" color="grey" flat unelevated></q-btn>
                    </div>
                </q-form>
            </q-card-section>
        </q-card>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      waktu: null,
      tujuan: null,
      harga: null
    }
  },
  methods: {
    onReset () {
      this.waktu = null
      this.tujuan = null
      this.harga = null
    },
    onSubmit () {
      this.$q.notify({
        type: 'positive',
        message: 'Berhasil Input Tiket Pesawat'
      })
      this.$router.push({ name: 'dashboard' })
    }
  }
}
</script>
