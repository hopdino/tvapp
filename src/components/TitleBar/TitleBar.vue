<template>
  <v-app-bar app dark style="-webkit-app-region: drag" height="52">
    <v-btn
      icon
      x-small
      rounded
      @click="close"
      class="menu-icon rounded-pill red ml-2"
    >
      <v-icon>mdi-close</v-icon>
    </v-btn>
    <v-btn
      icon
      x-small
      @click="min"
      class="menu-icon rounded-pill orange mx-2"
    >
      <v-icon>mdi-window-minimize</v-icon>
    </v-btn>
    <v-btn
      icon
      x-small
      @click="max"
      class="menu-icon rounded-pill green accent-3"
    >
      <v-icon>mdi-window-maximize</v-icon>
    </v-btn>

    <v-spacer></v-spacer>
    <v-spacer></v-spacer>
    <v-btn-toggle mandatory dense rounded>
      <v-btn text width="110">
        立即观看
      </v-btn>
      <v-btn text width="110">
        电影
      </v-btn>
      <v-btn text width="110">
        音乐
      </v-btn>
      <v-btn text width="110">
        探索
      </v-btn>
      <v-btn text width="110">
        资料库
      </v-btn>
    </v-btn-toggle>
    <v-spacer></v-spacer>
    <div>
      <v-text-field
        prepend-inner-icon="mdi-magnify"
        label="搜索"
        solo
        clearable
        dense
        dark
        hide-details
        background-color="#272727"
        class="my-text-style"
        style="width: 180px"
      ></v-text-field>
    </div>
  </v-app-bar>
</template>

<script>
const { ipcRenderer } = require('electron')

export default {
  name: 'TitleBar',
  methods: {
    min() {
      ipcRenderer.send('minimize')
    },
    max() {
      ipcRenderer.send('maximize')
    },
    close() {
      ipcRenderer.send('close')
    }
  }
}
</script>

<style scoped>
.my-text-style >>> .v-icon.theme--dark {
  color: gray !important;
}
.my-text-style >>> .v-label.theme--dark {
  color: gray !important;
}
.my-text-style >>> .v-input__slot {
  border: 1px solid rgba(171, 167, 171, 0.1) !important;
}
.my-text-style >>> .v-text-field__slot input {
  color: white !important;
}

.v-btn--icon.v-size--x-small {
  height: 12px;
  width: 12px;
}

.menu-icon >>> .mdi {
  font-size: x-small !important;
  color: black !important;
}
</style>

<!--深度作用选择器-->
