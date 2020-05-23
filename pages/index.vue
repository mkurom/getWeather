<template>
  <div>
    <section id="city-lists" class="section">
      <div class="container">
        <h1>日本全国の天気</h1>
        <ul>
          <li><nuxt-link :to="`city/sapporo`">札幌</nuxt-link></li>
          <li><nuxt-link :to="`city/sendai`">仙台</nuxt-link></li>
          <li><nuxt-link :to="`city/niigata`">新潟</nuxt-link></li>
          <li><nuxt-link :to="`city/tokyo`">東京</nuxt-link></li>
          <li><nuxt-link :to="`city/kanazawa`">金沢</nuxt-link></li>
          <li><nuxt-link :to="`city/nagoya`">名古屋</nuxt-link></li>
          <li><nuxt-link :to="`city/osaka`">大阪</nuxt-link></li>
          <li><nuxt-link :to="`city/kobe`">神戸</nuxt-link></li>
          <li><nuxt-link :to="`city/hiroshima`">広島</nuxt-link></li>
          <li><nuxt-link :to="`city/fukuoka`">福岡</nuxt-link></li>
          <li><nuxt-link :to="`city/naha`">那覇</nuxt-link></li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style>

</style>
