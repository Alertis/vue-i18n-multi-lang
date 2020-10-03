<template>
  <div class="hello">
    <button v-for="lang in languages" :key="lang.info.code" @click="changeLang(lang.info.code)" > {{ lang.info.name }}</button>
    <h1> {{ $t('title') }} </h1>
    <h2> {{ $t('links') }} </h2>
    <ul>
      <li> <a href="https://vuejs.org" target="_blank"> {{ $t('docs') }} </a> </li>
      <li> <a href="https://forum.vuejs.org" target="_blank"> {{ $t('forum') }} </a> </li>
      <li> <a href="https://chat.vuejs.org" target="_blank" > {{ $t('comChat') }} </a> </li>
      <li> <a href="https://twitter.com/vuejs" target="_blank" > Twitter </a> </li>
      <br>
      <li> <a href="http://vuejs-templates.github.io/webpack/" target="_blank" > {{ $t('templateDoc') }} </a> </li>
    </ul>
    <h2>{{ $t('ecosystem') }}</h2>
    <ul>
      <li> <a href="http://router.vuejs.org/" target="_blank" > vue-router </a> </li>
      <li> <a href="http://vuex.vuejs.org/" target="_blank" > vuex </a> </li>
      <li> <a href="http://vue-loader.vuejs.org/" target="_blank"> vue-loader </a> </li>
      <li> <a href="https://github.com/vuejs/awesome-vue" target="_blank" > awesome-vue </a> </li>
    </ul>
  </div>
</template>

<script>
import i18n from '@/plugins/i18n'
export default {
  name: 'HelloWorld',
  data: () =>{
      return {
          languages: Object.values(i18n.messages)
      }
  },
  methods:{
    changeLang: (lang) => {
      localStorage.setItem( "lang", lang )
      location.reload();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>
