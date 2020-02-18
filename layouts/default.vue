<template>
  <div>
    <section class="is-my-4">
      <div class="container has-text-centered">
        <nav id="main-nav">
          <ul>
            <li v-for="(item, index) in items" :key="index" class="is-mx-2">
              <nuxt-link :to="item.to.name">
                {{ item.title }}
              </nuxt-link>
            </li>
          </ul>
        </nav>
      </div>
    </section>
    <section class="section">
      <nuxt />
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: '/' }
        },
        {
          title: 'About',
          icon: 'people',
          to: { name: 'about' }
        },
        {
          title: 'Works',
          icon: 'works',
          to: { name: 'works' }
        }
      ]
    }
  }
}
</script>

<style lang="scss">
// navigation
#main-nav ul li {
  display: inline;
}
</style>
