<template>
    <div class="flex-col a-c">

    <div class="flex-col w100 a-c navTrav" v-if="navStat">
        <nav>
            <div class="nav-flex">
                <router-link to="/" style="color: black; text-decoration: none;"><img id="logo" src="@/assets/img/logo/logo.png" class="point" router to="/"></router-link>

                <div class="desktop-nav" v-if="!mobile">
                    <ul class="g-regular">
                        <li class="secondLiSet t-center g-regular"><span id="navItemContainer" :class="navList[0].class"><router-link to="/search-school" style="text-decoration: none; color: rgba(0,0,0,.5)">{{navList[0].content}}</router-link></span></li>
                        <li class="secondLiSet t-center g-regular"><span id="navItemContainer" :class="navList[1].class" v-html="navList[1].content"></span></li>
                        <li class="secondLiSet t-center g-regular"><span id="navItemContainer" :class="navList[2].class"  v-html="navList[2].content"></span></li>
                        <li class="secondLiSet t-center g-regular"><span id="navItemContainer" :class="navList[3].class" v-on:click="splitNavStatus = !splitNavStatus" v-html="navList[3].content"></span></li>
                        <li class="secondLiSet t-center g-regular"><span id="navItemContainer" :class="navList[4].class">{{navList[4].content}}</span></li>
                        <li class="secondLiSet t-center g-regular"><span id="navItemContainer" :class="navList[5].class">{{navList[5].content}}</span></li>
                    </ul>
                </div>

                <div class="burger-menu point flex-col a-c-n"  @click="burgerClick = !burgerClick" v-if="mobile">
                <div :class="{menu: true, 'turn-down': !burgerClick, slowDown: true}" id="bar-1"></div>
                <transition name="custom-classes-transition"
    enter-active-class="animated slideInRight"
    leave-active-class="animated slideOutRight">
                    <div class="menu" id="bar-2" v-if="burgerClick"></div>
                </transition>
                <div :class="{menu: true, 'turn-up': !burgerClick, slowDown: true}" id="bar-3"></div>
            </div>
            </div>
        </nav>
    </div>

    <div :class="{'menu-drop g-regular': true, drop: !burgerClick, undrop: burgerClick}">

        <div class="drop-menu-contain">
            <ul v-for="item in dropMenuItems" :key="item.id">
                <li>
                    <router-link :to="item.link" style="text-decoration: none; color: rgba(0,0,0,.5)" v-html="item.content" class="g-regular">{{item.content}}</router-link>
                </li>
            </ul>

            <div class="actOnDrop flex-col a-c g-regular" style="margin-top: 3rem;">
                <span class="loginBtn drop-act darkTxt point" v-if="!loggedIn">
                Login
                </span>
                <span class="startBtn green-act drop-act point" v-if="!loggedIn">
                Get Started
                </span>
                <span class="loginBtn green-act drop-act point" v-if="loggedIn">
                Logout
                </span>
            </div>
        </div>

    </div>

    </div>

</template>

<script>
export default {
  data () {
    return {
      burgerClick: true,
      navList: [{ content: 'Company', class: 'def', link: '/' }, { content: 'Rates', class: 'def', link: '/' }, { content: 'Products', class: 'def', link: '/' }, { content: 'Login', class: 'def', link: '/' }, { content: '|', class: 'def', link: '' }, { content: 'Get started', class: 'blue-btn', link: '/' }],
      travAgent: true,
      dropMenuItems: [
        { content: 'Company', class: 'def', link: '/ ', id: 1 }, { content: 'Rates', class: 'def', link: '/', id: 2 }, { content: 'Products', class: 'def', link: '/', id: 3 }
      ],
      loggedIn: false,
      navStat: true,
      mobile: false
    }
  },
  methods: {
  },
  updated () {
  },
  created () {
    // var route = this.$router.currentRoute.name
    if (window.innerWidth < 480) {
      this.mobile = true
    }
  }
}
</script>

<style scoped>
    @import url(~@/assets/styles/navbar.css);
</style>
