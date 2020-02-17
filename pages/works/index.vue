<template>
  <div class="container">
    <section class="section">
      <p v-for="(prj, i) in projects" :key="i">
        <card :title="prj.title" :content="prj.content" :imagePath="prj.imagePath" :demoUrl="prj.demoUrl" :repoUrl="prj.repoUrl" />
      </p>
    </section>
    <section class="has-text-centered section">
      <h1 class="title">
        Other project
      </h1>
      <sns :snsItems="snsItems" />
      <p>Click me!</p>
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
      snsItems: accounts.technicalItems

    }
  }
}

</script>

<style lang="scss" scoped>
</style>
