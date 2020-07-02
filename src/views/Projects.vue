<template>
  <div class="container">
    <h1>Projects</h1>
    <p>Projects I participated in and/or developed.</p>

    <GitHubCard
      title="My Blog"
      link="https://github.com/kurumiT3/kurumiT3.github.io"
      :info="BLOG"
      :loading="loading"
    >
      <p>
      
      </p>
    </GitHubCard>

    <GitHubCard
      title="portfolio"
      link="https://github.com/kurumiT3/portfolio"
      :info="portfolio"
      :loading="loading"
    >
      <p>
        Home Page
      </p>
    </GitHubCard>

    <GitHubCard
      title="📖 BIThesis"
      link="https://github.com/spencerwooo/Substats"
      :info="bithesisInfo"
      :loading="loading"
    >
      <p>
        LaTeX templates for your bachelor graduation thesis (and more) here at BIT.
      </p>
    </GitHubCard>

    
  </div>
</template>

<script>
import GitHubCard from '@/components/GitHubCard.vue'

export default {
  components: {
    GitHubCard,
  },
  data() {
    return {
      loading: true,
      dowwwInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      substatsInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      bithesisInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      fatesInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      dotfilesInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
    }
  },
  mounted() {
    const githubApiUrl = 'https://api.github.com/repos'

    const dowwwAxios = this.axios.get(`${githubApiUrl}/spencerwooo/dowww`)
    const substatsAxios = this.axios.get(`${githubApiUrl}/spencerwooo/Substats`)
    const bithesisAxios = this.axios.get(`${githubApiUrl}/spencerwooo/BIThesis`)
    const fatesAxios = this.axios.get(`${githubApiUrl}/SecureCats/Evaluation_BackEnd`)
    const dotfilesAxios = this.axios.get(`${githubApiUrl}/spencerwooo/dotfiles`)

    this.axios
      .all([dowwwAxios, substatsAxios, bithesisAxios, fatesAxios, dotfilesAxios])
      .then(
        this.axios.spread((...resp) => {
          this.loading = false
          this.dowwwInfo = resp[0].data
          this.substatsInfo = resp[1].data
          this.bithesisInfo = resp[2].data
          this.fatesInfo = resp[3].data
          this.dotfilesInfo = resp[4].data
        }),
      )
      .catch(err => {
        this.loading = false
        // eslint-disable-next-line no-console
        console.error(err)
      })
  },
}
</script>

<style scoped>
.container .github-project-card:not(:last-child) {
  margin-bottom: 40px;
}

p {
  line-height: 30px;
}
</style>
