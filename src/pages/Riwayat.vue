<template>
    <q-page>
      isi riwayat anda
    <div class="q-px-xs">
      Jenis Kelamin Anda
    </div>

      <div class="q-gutter-xs">
        <q-radio v-model="shape" val="pria" label="Pria" />
        <q-radio v-model="shape" val="perempuan" label="Perempuan" />
      </div>
    <div class="q-px-xs">
      Tanggal Lahir
    </div>
      <q-input outlined v-model="text" label="dd-mm-yyyy" />
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null,
      shape: null,

      accept: false
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'faris' && this.password === '18421054') {
        this.$q.notify({
          type: 'positive',
          message: 'nah sip cuk berhasil'
        })
        this.$router.push('/riwayat')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'waduh salah cuk, cek lagi username/password'
        })
      }
    },
    onReset () {
      console.log('ini fungsi reset')
      this.username = null
      this.password = null
      this.shape = null
      this.text = null
      this.accept = false
    }
  }
}
</script>
