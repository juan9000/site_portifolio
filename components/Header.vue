<template>
  <div class="container">
    <b-navbar>
      <template #brand>
          <b-navbar-item tag="router-link" :to="{ path: '/' }" style="justify-content: ">
            <img
              src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
              alt="Lightweight UI components for Vue.js based on Bulma"
            >
          </b-navbar-item>
      </template>

      <template #end>
        <b-navbar-item>
          <b-field>
              <b-switch v-model="$colorMode.preference"
                  true-value="dark"
                  false-value="ligth">
                  {{ $colorMode.preference == 'dark' ? 'Dark' : 'Ligth' }}-Mode
              </b-switch>
          </b-field>
        </b-navbar-item>
        <b-navbar-item>
          {{ language['presentation'] }}
        </b-navbar-item>
        <b-navbar-item>
          {{ language['portfolio'] }}
        </b-navbar-item>

        <b-navbar-dropdown :collapsible="true">
          <template #label class="dropdown-label">
            <CountryFlag :country="flag == 'br' ? 'br' : 'gb'" size='normal' style="margin-right: -9px" />
            <a>{{ language['language'] }}</a>
          </template>
          <b-navbar-item @click="changeLanguage('pt_BR')">
            <CountryFlag country='br' size='small' style="margin-right: -16px"/>
            Português Brasil
          </b-navbar-item>
          <b-navbar-item @click="changeLanguage('en_GB')">
            <CountryFlag country='gb' size='small' style="margin-right: -16px"/>
            English
          </b-navbar-item>
        </b-navbar-dropdown>
      </template>
    </b-navbar>
  </div>
</template>

<script>
import pt_BR from '~/utils/language/pt_BR'
import en_GB from '~/utils/language/en_GB'

export default {
  data () {
    return {
      language: pt_BR,
      flag: 'br',
    }
  },

  methods: {
    changeLanguage (lang) {
      if (lang == 'pt_BR') {
        this.language = pt_BR
        this.flag = 'br'
      } else {
        this.language = en_GB
        this.flag = 'gb'
      }
    },
  },

  created () {
    // se conexão for br pt_BR
  }

}
</script>
