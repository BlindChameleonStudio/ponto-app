<template>
  <div class="contactform pt-4">
      <v-card>
        <v-img class="test" src="https://static.parade.com/wp-content/uploads/2018/01/cute-cow-FTR.jpg" aspect-ratio="2.75" >
        </v-img>
        <v-card-title>
          <h2 class="display-1">Napište nám</h2>
        </v-card-title>
        <v-card-text>
          <v-form class="px-3" ref="form">
            <v-text-field label="Vaše Jméno" v-model="Name" prepend-icon="face" :rules="nameRules"></v-text-field>
            <v-text-field label="Váš Email" v-model="Email" prepend-icon="email" :rules="emailRules"></v-text-field>
            <v-textarea label="Vaše Zpráva" v-model="Content" prepend-icon="edit" :rules="contentRules"></v-textarea>
            <v-btn round class="info mx-0 mt-3" @click="submit">Odeslat</v-btn>
          </v-form>
        </v-card-text>

      </v-card>

  </div>

</template>
<script>
  export default {
    name: 'ContactForm',
    data () {
    return {
      Name: '',
      nameRules: [
        v => !!v || 'Je třeba vyplnit jméno'
      ],
      Email: '',
      emailRules: [
        v => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail musí mít platný formát'
        ]

      ,
      Content: '',
      contentRules: [
        v => v.length >= 20 || "Minimální počet znaků je 20"
      ]
    }
  },
  methods: {
    submit(){
      if(this.$refs.form.validate()){
      console.log(this.Name, this.Email, this.Content)
    }
    }
  }
}
</script>
<style>
.contactform {
  width: 40%;
}


</style>
