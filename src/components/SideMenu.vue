<template>
  <aside class="menu">
    <ul class="menu-list">
      <template v-for="(menuData, index) in menuDataList">
        <router-link
          :to="menuData.to"
          tag="li"
          class="menu-list-title"
          :key="index"
        >
          <a class="menu-list-title-link">{{menuData.title}}</a>
        </router-link>
      </template>
    </ul>
  </aside>
</template>

<script>
const MENU_DATA_LIST = [
  {
    title: '全体連絡',
    to: { name: 'General' },
  },
  {
    title: '雑談',
    to: { name: 'Chat' },
  },
  {
    title: '自己紹介',
    to: { name: 'SelfIntroduction' },
  }
];


export default {
  data() {
    return {
      menuDataList: MENU_DATA_LIST
    }
  }
}
</script>

<style scoped>
.menu {
  position: fixed;
  width: 199px;
  height: 100vh;
  background: #eee;
  border-right: 1px solid black;
}

.menu-list {
  list-style: none;
  margin: 0;
  padding: 0;
  text-align: center;
}

.menu-list-title {
  border-bottom: 1px solid black;
  height: 40px;
  line-height: 40px;
}

.menu-list-title-link {
  text-decoration: none;
  display: block;
  color: black;
  font-size: 0.8em;
}

.menu-list-title-link:hover,
.router-link-exact-active .menu-list-title-link {
  font-size: 1em;
  background-color: #555;
  color: white;
  font-weight: bold;
}
</style>