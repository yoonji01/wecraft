<template>
  <footer>
    <div class="container p-8">
          <div class="justify-between items-center">
            <span class="block font-black">© 2018 {{ site.title }} </span>
        <ul
          v-if="icons"
          class="pa-0 ma-0 list flex justify-between">
          <li
            v-for="(icon, index) in site.social"
            :key="index"
            :name=" '' + index "
            class="inline mr-3">
            <a
              :href="icon.href"
              class="text-grey-darkest hover:text-navy-lighter">
              <no-ssr>
                <v-icon
                  :name="'brands/' + icon.type"
                  scale="2" />
              </no-ssr>
            </a>
          </li>
        </ul>
        <div
          v-else
          class="bg-red-lightest border-l-4 border-red text-red-dark p-4"
          role="alert">
          <p class="font-bold">No icons</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import site from '~/content/site.json'

export default {
  data() {
    return {
      site: site,
      icons: site.social
    }
  }
}
</script>

<style lang="scss">
</style>
