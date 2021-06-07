<template>
  <div>
    <v-container>
      <v-card>
        <v-container>
          <v-subheader>회원가입</v-subheader>
          <v-form ref="form" v-model="valid" @submit.prevent="onSubmitForm">
            <v-text-field
              v-model="email"
              label="이메일"
              type="email"
              :rules="emailRules"
              required
            />
            <v-text-field
              v-model="password"
              label="비밀번호"
              type="password"
              :rules="passwordRules"
              required
            />
            <v-text-field
              v-model="passwordChk"
              label="비밀번호 확인"
              type="password"
              :rules="passwordChkRules"
              required
            />
            <v-text-field
              v-model="nickname"
              label="닉네임"
              type="text"
              :rules="nicknameRules"
              required
            />
            <v-checkbox
              v-model="terms"
              label="광고 수신 동의합니까"
              :rules="[v => !!v || '약관에 필수로 동의해야합니다']"
              required
            />
            <v-btn color="green" type="submit" :disabled="!valid">가입하기</v-btn>
          </v-form>
        </v-container>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      valid: false,
      email: '',
      password: '',
      passwordChk: '',
      nickname: '',
      terms: false,
      emailRules: [
          v => !!v || '이메일은 필수입니다.',
          v => /.+@.+/.test(v) || '이메일이 유효하지 않습니다.'
      ],
      nicknameRules: [
          v => !!v || '닉네임은 필수입니다'
      ],
      passwordRules: [
          v => !!v || '비밀번호는 필수입니다'
      ],
      passwordChkRules: [
          v => !!v || '비밀번호확인은 필수입니다',
          v => v === this.password || '비밀번호가 다릅니다'
      ],
    }
  },
  head: {
    title: '회원가입'
  },
  methods: {
    onSubmitForm(){
      if(this.$refs.form.validate()) {
        alert('성공')
      } else {
        alert('실패')
      }
    }
  },
}
</script>

<style scoped>

</style>
