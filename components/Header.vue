<template>
  <div class="container">
    <b-navbar>
      <template #brand>
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <img
            src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
            alt="Lightweight UI components for Vue.js based on Bulma"
          >
        </b-navbar-item>
        <a>asdadas</a>
      </template>

      <template #end>
        <b-navbar-item>
          <b-field>
              <b-switch v-model="$colorMode.preference"
                  true-value="dark"
                  false-value="ligth">
                  {{ $colorMode.preference }}-mode
              </b-switch>
          </b-field>
        </b-navbar-item>
        <b-navbar-item>
          {{ language['presentation'] }}
        </b-navbar-item>

        <b-navbar-item>
          {{ language['portfolio'] }}
        </b-navbar-item>

        <b-navbar-dropdown label="Info" :collapsible="true">
          <b-navbar-item @click="changeLanguage('pt_BR')">
            Português Brasil
          </b-navbar-item>
          <b-navbar-item @click="changeLanguage('en_GB')">
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
      language: pt_BR
    }
  },

  methods: {
    changeLanguage (lang) {
      if(lang == 'pt_BR'){
        this.language = pt_BR
      }else{
        this.language = en_GB
      }
    }
  },

  created () {
    // se conexão for br pt_BR
  }

}
</script>
