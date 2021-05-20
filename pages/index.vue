<template>
  <div class="container">
    <CBox
      v-bind="colorMode"
      d="flex"
      w="100vw"
      h="100vh"
      flex-dir="column"
      justify-content="center"
    >
      <CFlex m="1" justify="flex-start">
        <DarkMoodBtn @changeMode="colorMode = $event" />
        <c-button pos="absolute" top="0" right="0" m="2" text-decoration="none">
          <c-link as="router-link" to="/dashboard" text-decoration="none">
            Dashboard
          </c-link>
        </c-button>
      </CFlex>
      <CFlex h="100vh" justify="center" direction="column" align="center">
        <CBox>
          <c-image :src="require('@/assets/logo.png')" alt="Jonathan Bakebwa" />
        </CBox>
      </CFlex>
    </CBox>
  </div>
</template>

<script lang="js">
export default {
  name: 'App',

  data(){
    return {
      colorMode: {}
    }
  }
}
</script>
