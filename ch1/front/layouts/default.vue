<template>
  <div>
    <v-app>
      <!-- nav -->
      <nav>
        <v-toolbar dark color="green">
          <v-toolbar-title>
            <nuxt-link to="/">NodeBird</nuxt-link>
          </v-toolbar-title>
          <v-spacer />
          <v-toolbar-items>
            <v-text-field label="검색" hide-details prepend-icon="mdi-magnify" :style="{alignItems: 'center'}" />
            <v-btn text nuxt to="/profile"><div>프로필</div></v-btn>
            <v-btn text nuxt to="/signup"><div>회원가입</div></v-btn>
          </v-toolbar-items>
        </v-toolbar>
      </nav>
      <!-- //nav -->

      <v-row no-gutters>
        <v-col cols="12" md="4">
          <login-form />
        </v-col>
        <v-col cols="12" md="8">
          <nuxt />
        </v-col>
      </v-row>
    </v-app>
  </div>
</template>

<script>
import LoginForm from '~/components/LoginForm';

export default {
  components: {
    LoginForm
  }
}
</script>

<style scoped>

</style>
