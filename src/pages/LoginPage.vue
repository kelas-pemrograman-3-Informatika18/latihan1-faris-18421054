<template>

    <q-page class="bg-yellow-5">
    <div class="row">
    <q-card class="fixed-center col-md-4 col-xs-12 bg-white" flat>
      <div class="header">
        Halaman Login
      </div>
         <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="username lu cuk *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Isi cuk']"
      />

      <q-input
        filled
        type="Password"
        v-model="password"
        label="Password *"
        lazy-rules
        :rules="[ val => val !== null && val.length > 0 || 'Isi password lu cuk']"
      />
      <div class="button">
      <q-btn label="Submit" type="submit" color="primary"/>
      <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </q-card>
    </div>
    </q-page>
</template>

<style lang="sass" scoped>
  .header
    font-size: 24px
    font-weight: 'bold'
    font-family: 'century gothic'
    padding: 10px 15px
  .row
    padding: 10px 15px
  .button
    padding: 10px 15px
  .row + .row
    margin-top: 1rem
</style>

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
