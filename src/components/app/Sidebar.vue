<template>
    <ul class="sidenav app-sidenav" :class="{open: value}">

      <router-link
      v-for="link in links"
      :key="link.to"
        tag="li"
        active-class="active"
        :to="link.to"
        :exact="link.exact"
      >
        <a href="#" class="waves-effect waves-orange pointer">{{link.title}}</a>
      </router-link>
    </ul>
</template>

<script>
import localizeFilter from '@/filters/localize.filter'
export default {
  props: ['value'],
    data: () => ({
        links: [
           {title: localizeFilter('Menu_Bill'), to: '/', exact: true},
           {title: localizeFilter('Menu_History'), to: '/history'},
           {title: localizeFilter('Menu_Planning'), to: '/planning'},
           {title: localizeFilter('Menu_Record'), to: '/record'},
           {title: localizeFilter('Menu_Categories'), to: '/categories'}
        ]
    })
}
</script>