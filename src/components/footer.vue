<template>
  <div class="footer">
    <ul v-for="list in category" class="list">
      <li class="title">{{ list.title }}</li>
      <li v-for="item in list.linkList">
        <a :href="item.link" target="_blank">{{ item.name }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
import {defineComponent, readonly} from 'vue'

export default defineComponent({
  name: 'mFooter',
  setup() {
    let category = readonly([
      {
        title: '仅供学习交流使用',
        linkList: [
          {name: '联系方式QQ', link: 'https://qm.qq.com/cgi-bin/qm/qr?k=X9ZaT4fO-WKFRP0H0NWw155HYzPq5WLD&noverify=0'},
          {name: '联系方式telegram', link: 'https://t.me/Web3defi'},
        ]
        
      }
    ])
    return { category }
  }
})
</script>

<style scoped>
.footer {
  display: flex;
  padding: 2em 5%;
  background: #222;
}
.footer .list {
  list-style: none;
  margin-right: 5%;
}
.footer .list li {
  margin-bottom: 0.3em;
}
.footer .list li.title {
  font-size: 18px;
  font-weight: 300;
  color: #fff;
  margin-bottom: 0.5em;
}
.footer .list li a {
  color: #fff;
  font-size: 14px;
}
</style>