<template>
  <header>
      <div class="wrapper">
          <v-app-bar :elevation="2">
              <v-app-bar-title>Wordle 2: Electric Boogaloo</v-app-bar-title>
              <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
          </v-app-bar>

          <v-navigation-drawer v-model="drawer" absolute bottom temporary>
              <v-list nav dense>
                  <v-list-item-group v-model="group">
                      <v-list-item>
                          <nav>
                              <RouterLink to="/wordle">Wordle</RouterLink>
                          </nav>
                      </v-list-item>

                      <v-list-item>
                          <nav>
                             <RouterLink to="/about">About</RouterLink>
                          </nav>
                      </v-list-item>

                  </v-list-item-group>
              </v-list>
          </v-navigation-drawer>

          <v-btn @click="setInverseTheme"> Inverse Theme </v-btn>
          <v-btn @click="setDarkTheme"> Dark Theme </v-btn>
      </div>
  </header>

  <RouterView />
</template>

<script setup lang="ts">
import { useTheme } from 'vuetify/lib/framework.mjs'

const theme = useTheme()

function setInverseTheme() {
  theme.global.name.value = 'inverse'
}

function setDarkTheme() {
  theme.global.name.value = 'dark'
}
</script>
