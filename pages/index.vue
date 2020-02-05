<template>
  <div class="container">
    <section class="has-text-centered">
      <h1 class="title">
        simics-ja
      </h1>
      <ul>
        <li v-for="(item, index) in snsItems" :key="index">
          <a :href="item.url">
            <b-icon :icon="item.icon.name" :pack="item.icon.pack" size="is-large" />
          </a>
        </li>
      </ul>
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
