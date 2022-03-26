<template>
  <div class="bg-primary position-relative">
    <div class="cont-header-bottom container d-flex">
      <div class="cont-img d-flex align-items-center">
        <img class="w-100 my-auto" src="../../assets/img/f1_logo.svg" alt="">
      </div>
      <ul class="list-inline d-flex mb-0 ms-4">
        <li class="menu-princ list-inline-items h-100 d-flex align-items-center"
          v-for="(item, index) in arrMenu" 
          :key="index" 
          :class="{'active':item.active}" 
          @mouseover="currentIndex= index; item.active= true"
          @mouseout="item.active= false" >
          <div class="mx-3 m-auto">
            <a class="text-light text-decoration-none" :class="{'active':item.active}" :href="item.href">{{ item.title }}</a>
          </div>
        </li>
      </ul>

      <div v-if="currentIndex== 4" :class="{'drop--active':currentIndex== 4}" class="drop-menu position-absolute text-light">
        <drop-driver-menu :arrDriver= arrDriver />
      </div>
      
      <div v-if="currentIndex== 5" :class="{'drop--active':currentIndex== 5}" class="drop-menu position-absolute text-light">
        <drop-team-menu :arrTeam= arrTeam />
      </div>

    </div>
  </div>
</template>

<script>
import DropDriverMenu from '../DropMenu/DropDriverMenu.vue'
import DropTeamMenu from '../DropMenu/DropTeamMenu.vue'

export default {
  name: 'HeaderBottom',
  data () {
    return {
      currentIndex: 0
    }
  },
  components: { 
    DropDriverMenu,
    DropTeamMenu 
  },
  props: {
    arrMenu: Array,
    arrDriver: Array,
    arrTeam: Array
  }

}
</script>

<style scoped lang="scss">
.cont-header-bottom {
  min-width: 960px;
  height: 70px;
  font-weight: 400;
  font-size: 1.1rem;
  .cont-img {
    width: 140px;
    height: 100%;
  }
  li.menu-princ {
    cursor: pointer;
    transition: background .25s;
      &:hover {
    background-color: #000;
    }
    
    a {
      display: block;
      padding: .1rem .7rem;
      border: 1px solid transparent;
      border-top: 0;
      border-left: 0;
      border-end-end-radius: 8px;
    }
    a.active {
      border-color: #fff;

    }
  }
  li.active {
    background-color: #000;
  }
  .drop-menu {
    top:70px;
    left:0;
    right: 0;
    background-color: #15151e;
    height: 0;
    overflow: hidden;
    border-bottom:0;
    opacity: 0;
    li:hover {
      background-color: #000;
    }
  }
  .drop--active {
    opacity: 1;
    height: auto;
    border-bottom: 1px solid #e10600;
  }
}
</style>