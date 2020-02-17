<template>
  <div class="container">
    <section class="has-text-centered section">
      <h1 class="title">
        simics-ja
      </h1>
      <sns :snsItems="snsItems" class="is-mb-3" />
    </section>
    <section class="has-text-centered">
      <div id="hatena-viewer" class="has-text-centered">
        <h2>
          INTEREST TOPIC
        </h2>
        <div class="is-size-7 is-mx-auto">
          <ul>
            <li v-for="(item, i) in hatena" :key="i" class="is-mb-1">
              <p class="hatena-date">
                {{ item['dc:date'][0] | truncate(10, '') }}
              </p>
              <p class="hatena-title">
                <a :href="item.link[0]">
                  {{ item.title[0] | truncate(70, '...') }}
                </a>
              </p>
              <p class="hatena-tag has-text-right is-block">
                <ul>
                  <li v-for="(tag, j) in item['dc:subject']" :key="j" class="is-inline is-ml-1">
                    <a :href="tag | prefix('https://b.hatena.ne.jp/simics-ja/')" class="has-text-accent">{{ tag }}</a>
                  </li>
                </ul>
              </p>
            </li>
          </ul>
        </div>
        <p>
          From <a href="https://b.hatena.ne.jp/simics-ja/">Hatena Bookmark</a>
        </p>
      </div>
    </section>
  </div>
</template>

<script>
import accounts from '~/assets/jsons/accounts.json'
import sns from '~/components/SNS'

export default {
  components: {
    sns
  },
  filters: {
    truncate (string, limit, suffix) {
      if (string) {
        return string.substring(0, limit) + (string.length > limit ? suffix : '')
      } else {
        return ''
      }
    },
    prefix (string, prefix) {
      return prefix + string
    }
  },
  data () {
    return {
      snsItems: accounts.snsItems
    }
  },
  async asyncData (store) {
    const hatena = await store.$axios.get('https://get-request-repeater.simics-ja.now.sh/api/my-hatena-rss').then((results) => {
      const parseString = require('xml2js').parseStringPromise
      const xml = results.data
      return (
        async (xml) => {
          const parsedItems = await parseString(xml)
            .then((parsed) => {
              return parsed['rdf:RDF'].item
            })
            .catch((e) => {
              return []
            })
          return parsedItems
        }
      )(xml)
    })

    return {
      hatena
    }
  }
}

</script>

<style lang="scss" scoped>
#hatena-viewer {
  display: inline;
}
#hatena-viewer div {
  max-width: 600px;
  padding: 1rem;
  border: solid 1px #EAEAFF;
  border-radius: 1rem;
  word-wrap : break-word;
  overflow-wrap : break-word;
  ul li {
    display: block;
    text-align: left;
    .hatena-tag {
      display: inline-block;
    }
  }
}
</style>
