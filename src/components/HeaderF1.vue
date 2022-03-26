<template>
  <div>
      <header-top />
      <header-bottom 
        :arrMenu= arrMenu 
        :arrDriver= arrDriver 
        :arrTeam= arrTeam
      />
  </div>
</template>

<script>
import HeaderTop from './HeaderF1/HeaderTop.vue'
import HeaderBottom from './HeaderF1/HeaderBottom.vue'

export default {
  name: 'HeaderF1',
  components: {
    HeaderTop,
    HeaderBottom
  },
  data () {
    return {
      arrMenu: [
        {
          title: 'Lastest',
          href: '#',
          active: false
        },
        {
          title: 'Video',
          href: '#',
          active: false
        },
        {
          title: 'Schedule',
          href: '#',
          active: false
        },
        {
          title: 'Standings',
          href: '#',
          active: false
        },
        {
          title: 'Drivers',
          href: '#',
          active: false,
          content: [
            {
              name: ''
            }
          ]
        },
        {
          title: 'Team',
          href: '#',
          active: false
        },
        {
          title: 'Gaming',
          href: '#',
          active: false
        },
        {
          title: 'Timing',
          href: '#',
          active: false
        },
      ]
    }
  },
  props: {
    arrDriver: Array,
    arrTeam: Array
  }
}
</script>

<style scoped lang="scss">

</style>