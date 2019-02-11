<template>
  <div class="contactform pt-4">
      <v-card>
        <v-img class="cardimage" :src="require('../assets/cardcow.jpg')" aspect-ratio="2.75" />
        <v-card-title>
          <!-- <h2 class="display-1 ml-3">Napište nám</h2> -->
        </v-card-title>
        <v-card-text>
          <v-form class="px-3" ref="form">
            <v-text-field label="Vaše Jméno" v-model="name" prepend-icon="face" :rules="nameRules"></v-text-field>
            <v-text-field label="Váš Email" v-model="email" prepend-icon="email" :rules="emailRules"></v-text-field>
            <v-textarea label="Vaše Zpráva" v-model="content" prepend-icon="edit" :rules="contentRules"></v-textarea>
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
      name: '',
      email: '',
      content: '',
      nameRules: [
        v => !!v || 'Je třeba vyplnit jméno'
      ],
      emailRules: [
        v => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail musí mít platný formát'
        ],
      contentRules: [
        v => v.length >= 20 || "Minimální počet znaků je 20"
      ]
    }
  },
  methods: {
    submit(){
      if(this.$refs.form.validate()){ // Bez tohohle me to necha postnout i kdyz nemam splneny podminky (sice to rve ze to ma mit urcitej length, ale odeslat to lze)
      console.log(this.name, this.email, this.content)
    }
    }
  }
}
</script>
<style>
.contactform {
  width: 40%;
}

.cardimage {
  width: 100%;
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;

}

</style>
