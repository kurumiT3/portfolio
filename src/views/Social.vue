<template>
  <div class="container">
    <h1>Social</h1>
    <p>Some of my followers.</p>

    <div class="col-container">
      <div class="row-container">
        <statCard
          statTitle="Telegram Channel"
          :followers="telegram.data"
          suffix="members"
          icon="telegram.png"
          :loading="telegram.loading"
          link="https://t.me/kurumit3"
        />
        <statCard
          statTitle="QQ（1817855234）"
          :followers="160"
          suffix="friends"
          icon="QQ.png"
          :loading="twitter.loading"
          link="https://wpa.qq.com/msgrd?v=3&uin=1817855234&site=qq&menu=yes"
        /> 
        </div>
        <div class="row-container">
        <statCard
          statTitle="SSPAI"
          :followers="sspai.data"
          suffix="followers"
          icon="sspai.png"
          :loading="sspai.loading"
          link="https://sspai.com/u/kurumit3/posts"
        />
        <statCard
          statTitle="Douban"
          :followers="1"
          suffix="followers"
          icon="douban.png"
          :loading="twitter.loading"
          link="https://www.douban.com/people/kurumit3/"
        /> 
      </div>
      <div class="row-container">
        <statCard
          statTitle="Weibo"
          :followers="weibo.data"
          suffix="fans"
          icon="weibo.png"
          :loading="weibo.loading"
          link="https://weibo.com/kurumit3"
        />
        <statCard
          statTitle="Zhihu"
          :followers="zhihu.data"
          suffix="followers"
          icon="zhihu.png"
          :loading="zhihu.loading"
          link="https://www.zhihu.com/people/ni-lu-guang"
        />
      </div>
      <div class="row-container">
        <statCard
          statTitle="Twitter"
          :followers="twitter.data"
          suffix="followers"
          icon="twitter.png"
          :loading="twitter.loading"
          link="https://twitter.com/Nightma34781407"
        />
        <statCard
          statTitle="GitHub"
          :followers="github.data"
          suffix="followers"
          icon="github.png"
          :loading="github.loading"
          link="https://github.com/kurumiT3"
        />
      </div>
      <div class="row-container">
        <statCard
          statTitle="Bilibili"
          :followers="12"
          suffix="followers"
          icon="bilibili.png"
          :loading="twitter.loading"
          link="https://space.bilibili.com/351869081"
        />
        <statCard
          statTitle="Coolapk"
          :followers="513"
          suffix="fans"
          icon="coolapk.png"
          :loading="twitter.loading"
          link="http://www.coolapk.com/u/1723860"
        /> 
      </div>
    </div>

    <p id="substats-footer">
      * Follower statistics powered by:
      <a href="https://api.spencerwoo.com/substats">Substats</a>.
    </p>
  </div>
</template>

<script>
import statCard from '@/components/StatCard.vue'

export default {
  components: {
    statCard,
  },
  data() {
    return {
      sspai: { data: 0, loading: true },
      zhihu: { data: 0, loading: true },
      weibo: { data: 0, loading: true },
      twitter: { data: 0, loading: true },
      github: { data: 0, loading: true },
      telegram: { data: 0, loading: true },
    }
  },
  mounted() {
    const apiUrl = 'https://api.spencerwoo.com/substats'
    const zhihuAxios = this.axios.get(`${apiUrl}/?source=zhihu&queryKey=ni-lu-guang`)
    const weiboAxios = this.axios.get(`${apiUrl}/?source=weibo&queryKey=6482844382`)
    const twitterAxios = this.axios.get(`${apiUrl}/?source=twitter&queryKey=Nightma34781407`)
    const githubAxios = this.axios.get(`${apiUrl}/?source=github&queryKey=kurumiT3`)
    const telegramAxios = this.axios.get(`${apiUrl}/?source=telegram&queryKey=kurumit3`)
    const sspaiAxios = this.axios.get(`${apiUrl}/?source=sspai&queryKey=kurumit3`)

   
    
    zhihuAxios.then(r => {
      this.zhihu = { data: r.data.data.totalSubs, loading: false }
    })
    weiboAxios.then(r => {
      this.weibo = { data: r.data.data.totalSubs, loading: false }
    })
    twitterAxios.then(r => {
      this.twitter = { data: r.data.data.totalSubs, loading: false }
    })
    sspaiAxios.then(r => {
      this.sspai = { data: r.data.data.totalSubs, loading: false }
    })
    githubAxios.then(r => {
      this.github = { data: r.data.data.totalSubs, loading: false }
    })
    telegramAxios.then(r => {
      this.telegram = { data: r.data.data.totalSubs, loading: false }
    })
  },
}
</script>

<style lang="css" scoped>
.col-container {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: stretch;
  align-content: center;
}

.row-container {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: stretch;
  align-content: stretch;
  margin: 15px 0px;
}

.row-container .statCard:last-child {
  margin-left: 30px;
}

.row-container .statCard {
  flex: 1;
}

@media screen and (max-width: 760px) {
  .row-container {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: flex-start;
    align-items: stretch;
    align-content: center;
  }

  .row-container .statCard:last-child {
    margin-left: 0px;
    margin-top: 30px;
  }
}

a {
  text-decoration: none;
}

p {
  line-height: 30px;
}

#substats-footer {
  color: #666666;
  text-align: left;
}
</style>
