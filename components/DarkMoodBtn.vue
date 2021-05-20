<template>
    <CIconButton
      :icon="colorMode === 'light' ? 'moon' : 'sun'"
      :aria-label="`Switch to ${colorMode === 'light' ? 'dark' : 'light'} mode`"
      @click="toggleColorMode"
    />
</template>

<script lang="js">
export default {
  name: "dark-mood-btn",

  data () {
    return {
      mainStyles: {
        dark: {
          bg: 'gray.700',
          color: 'whiteAlpha.900'
        },
        light: {
          bg: 'white',
          color: 'gray.900'
        }
      }
    }
  },
  
  inject: [
    '$chakraColorMode',
    '$toggleColorMode'
  ],

  computed: {
    colorMode () {
      return this.$chakraColorMode()
    },
    
  },

  methods:{
    toggleColorMode () {
      this.$toggleColorMode();
      this.$emit('changeMode', this.mainStyles[this.colorMode]);
    }
  }
}
</script>
