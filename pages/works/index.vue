<template>
  <div class="container">
    <section class="has-text-centered section">
      <h1 class="title">
        Works
      </h1>
      <div>
        <div v-for="(prj, i) in projects" :key="i">
          <card :title="prj.title" :content="prj.content" :imagePath="prj.imagePath" :links="prj.links" />
        </div>
      </div>
    </section>
    <section class="has-text-centered section">
      <h1 class="title">
        Other repository
      </h1>
      <sns :snsItems="snsItems" />
      <p>Click me!</p>
    </section>
    <section class="has-text-centered section">
      <h1 class="title">
        Design
      </h1>
      <p v-for="(prj, i) in designs" :key="i">
        <card :title="prj.title" :content="prj.content" :imagePath="prj.imagePath" :links="prj.links" />
      </p>
    </section>
  </div>
</template>

<script>
import items from 'assets/jsons/projects.json'
import accounts from 'assets/jsons/accounts.json'
import card from '~/components/Card'
import sns from '~/components/SNS'

require.context('assets/images/portfolio', false, /\.png$/)

export default {
  components: {
    card,
    sns
  },
  data () {
    return {
      projects: items.projects,
      designs: items.designs,
      snsItems: accounts.technicalItems
    }
  }
}

</script>

<style lang="scss" scoped>
</style>
