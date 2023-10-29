<template>
  <div class="q-pa-md" style="max-width: 400px">

    <q-form
      @submit="onSubmit"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="user"
        label="Usuario *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
        filled
        v-model="password"
        type="password"
        label="AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <div>
        <q-btn label="Entrar" type="submit" color="primary"/>
      </div>
    </q-form>

  </div>
</template>

<script>
import { defineComponent } from 'vue'
import { useQuasar } from 'quasar'
import { ref } from 'vue'

export default defineComponent({
  name: 'CadastroPage',
  setup () {
    const $q = useQuasar()

    const user = ref(null)
    const password = ref(null)


    return {
      user,
      password,

      onSubmit () {
          $q.notify({
            color: 'green-4',
            textColor: 'white',
            icon: 'cloud_done',
            message: 'Submitted'
          })
        
      }
    }
  }
});
</script>
