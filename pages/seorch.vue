<template>
  <center><v-form v-model="valid">
    <v-flex xs12 sm6 md3>
          <v-text-field
            label=""
            solo
          ></v-text-field>
        </v-flex>
     <v-btn color="primary" dark @click="Dologin">ค้นหา
        <v-icon dark right>label</v-icon>
      </v-btn>
  </v-form></center>
</template>
<script>
  export default {
    data: () => ({
      valid: false,
      show1: false,
       password: '',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          emailMatch: () => ('The email and password you entered don\'t match')
        },
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
      ]
    }),
    methods:{
      async Dologin(){
        console.log (this.email)
        console.log (this.password)
        let res = await this.$http.post('http://127.0.0.1/php_test/login.php', {
          user : this.email,
          pass : this.password
        })
        if (res.data.ok){
          this.$router.push('/table')
        }
      },
      Dosave(){
        this.email='',
        this.password=''
      }
    }
  }
</script>