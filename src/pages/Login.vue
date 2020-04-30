<template>
  <q-page class="bg-teal-2">
    <div class="row">
      <q-card class="fixed-center col-md-4 col-xs-12 bg-blue-8" flat>
        <q-card-section>
          <div class="text-h6 q-pb-md">
            Halaman Login
          </div>
          <q-form
            @submit="onSubmit"
            @reset="onReset"
            class="q-gutter-md"
          ><u></u>
            <q-input
              filled
              v-model="username"
              label="Username Anda"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Masukkan Username']"
            />

            <q-input
              filled
              type="password"
              v-model="password"
              label="Password Anda"
              lazy-rules
              :rules="[
                val => val !== null && val.length > 0 || 'Password Tidak Boleh Kosong'
              ]"
            />
            <div class="q-gutter-md">
              <q-btn label="Login" type="submit" color="primary"/>
              <q-btn label="Register" to="/register" flat color="red"/>
              <!--<q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />-->
            </div>
        </q-form>
        </q-card-section>
    </q-card>
    </div>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'destriandre' && this.password === '11111') {
        this.$q.notify({
          type: 'positive',
          message: 'Selamat! Anda Berhasil Login'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'Gagal Login, Username/Password Anda Salah'
        })
      }
    },
    onReset () {
      this.username = null
      this.password = null
    }
  }
}
</script>
