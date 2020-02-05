<template>
  <div class="container">
    <section class="has-text-centered">
      <h1 class="title">
        simics-ja
      </h1>
      <div id="social-media-icons" class="is-mb-3">
        <ul class="title">
          <li v-for="(item, index) in snsItems" :key="index">
            <a :href="item.url">
              <b-icon :icon="item.icon.name" :pack="item.icon.pack" size="is-large" />
            </a>
          </li>
        </ul>
      </div>
    </section>
    <section class="has-text-centered">
      <h2>
        INTERST TOPIC
      </h2>
      <div />
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      snsItems: [
        {
          title: 'github',
          icon: { name: 'github', pack: 'fab' },
          url: 'https://github.com/simics-ja/'
        },
        {
          title: 'twitter',
          icon: { name: 'twitter', pack: 'fab' },
          url: 'https://twitter.com/simics_ja/'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
// social media
#social-media-icons ul li {
  display: inline;
}
</style>
