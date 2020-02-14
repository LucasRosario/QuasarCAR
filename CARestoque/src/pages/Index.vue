<template>
  <q-page class="flex flex-center">

    <div class="q-pa-xl border-red">

    <q-form @submit="onSubmit" @reset="onReset" class="q-pa-xl border-black">
      <q-img
        class="m-pa-auto border-red"
        :src="url"
        spinner-color="white"
      ></q-img>

      <q-input
        class="q-pa-sm"
        rounded outlined
        v-model="email"
        type="email"
        label="Digite o e-mail">
      </q-input>
      <q-input
      class="q-pa-sm"
       rounded outlined
       v-model="password"
       :type="isPwd ? 'password' : 'text'"
       label="Digite a senha">
        <template v-slot:append>
          <q-icon
            :name="isPwd ? 'visibility_off' : 'visibility'"
            class="cursor-pointer"
            @click="isPwd = !isPwd"
          ></q-icon>
        </template>
      </q-input>

      <div>
        <q-btn label="Entrar" type="submit" color="secondary"/>
        <q-btn label="Esqueci a senha" type="reset" color="secondary" flat class="q-ml-sm" />
      </div>
    </q-form>

  </div>

  </q-page>
</template>
<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      url: '../statics/logo-car.png',
      password: '',
      isPwd: true,
      email: ''
    }
  },

  methods: {
    onSubmit () {
      if (this.accept !== true) {
        this.$q.notify({
          color: 'red-5',
          textColor: 'white',
          icon: 'warning',
          message: 'You need to accept the license and terms first'
        })
      } else {
        this.$q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: 'Submitted'
        })
      }
    },

    onReset () {
      this.name = null
      this.age = null
      this.accept = false
    }
  }
}
</script>
