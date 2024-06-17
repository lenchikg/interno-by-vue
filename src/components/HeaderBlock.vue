<template>
    <header class="header">
        <div class="header__container">
            <a href="#" class="header__logo">
                <img src="../img/logo.svg" alt="" />
            </a>
            <nav class="header__menu menu">
                <ul class="menu__list">
                    <li class="menu__item">
                        <router-link to="/">Home</router-link>
                        <!-- <a class='menu__link' href='index.html'>Home</a> -->
                    </li>
                    <!-- <li class="menu__item">
                        <a class='menu__link' href='/about'>About Us</a>
                    </li> -->
                    <!-- <li class="menu__item">
                        <a class='menu__link' href='/services'>Services</a>
                    </li> -->
                    <li class="menu__item">
                        <router-link to="/ArticlesPage">Articles</router-link>
                        <!-- <a class='menu__link' href='articlesFilter.html'>Articles Filter</a> -->
                    </li>
                    <li class="menu__item">
                        <router-link to="/ProjectsPage" class='menu__link'>Projects</router-link>
                        <!-- <a class='menu__link' href='articlesSort.html'>Articles Sort</a> -->
                    </li>
                    <li class="menu__item">
                        <router-link to="/ProjectPage" class='menu__link'>Project</router-link>
                        <!-- <a class='menu__link' href='projects.html'>Projects</a> -->
                    </li>
                    <!-- <li class="menu__item">
                        <a class='menu__link' href='project.html'>Project</a>
                    </li> -->
                    <li class="menu__item">
                        <router-link to="/BlogPage" class='menu__link'>Blog</router-link>
                        <!-- <a class='menu__link' href='blog.html'>Blog</a> -->
                    </li>
                    <!-- //popup -->
                    <!-- <li class="menu__item">
                        <button class="menu-btn" @click="openPopupMenu">PopUp</button>
                    </li> -->
                </ul>
            </nav>
            <div class="header__actions">
                <a href="#" class="header__search" @click="openPopupSearch">
                    <img src="../img/icons/search.svg" alt="search" />
                </a>
                <div class="header__burger icon-menu" @click="openPopupMenu">
                    <span></span>
                </div>
            </div>
            <PopupMenu ref="popupMenu" />
            <PopupSearch ref="popupSearch" />
        </div>
    </header>
</template>

<script>
import PopupMenu from '@/components/PopupMenu.vue'
import PopupSearch from '@/components/PopupSearch.vue'

export default {
  name: 'HeaderBlock',

  components: {
    PopupMenu,
    PopupSearch
  },

  data () {
    return {

    }
  },

  mounted () {

  },

  computed: {

  },

  methods: {
    openPopupMenu () {
      this.$refs.popupMenu.openPopup()
    },
    openPopupSearch () {
      this.$refs.popupSearch.openPopup()
      // почему только в PopupSearchPage2 в Вы искали: "" попадает то что надо. что за магия?
      this.$router.push({ name: 'PopupSearchPageНЕСУЩЕСТВЮИЩАЯРАБОТАЕТ', params: { query: this.searchQuery } })
      // Очищаем поисковую строку
      this.searchQuery = ''
    }
    // так не показыват оно поиска при клике
    // openPopupSearch () {
    //   // Проверяем, находится ли пользователь на странице поиска
    //   if (this.$route.name === 'PopupSearchPage' && this.$route.params.query === this.searchQuery) {
    //     // Если да, то не выполняем переход
    //     return
    //   }
    //   // Если пользователь не находится на странице поиска, выполняем переход
    //   this.$router.push({ name: 'PopupSearchPage', params: { query: this.searchQuery } })
    // }
  }
}
</script>

<style lang="css" scoped>

</style>
