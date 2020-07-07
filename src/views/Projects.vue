<template>
  <div class="container">
    <h1>Projects</h1>
    <p>Projects I participated in and/or developed.</p>

    <GitHubCard
      title="My Blog"
      link="https://github.com/kurumiT3/kurumiT3.github.io"
      :info="My BlogInfo"
      :loading="loading"
    >
      <p>
      My Blog Site (Theme:cards)
      </p>
    </GitHubCard>

    <GitHubCard
      title="portfolio"
      link="https://github.com/kurumiT3/portfolio"
      :info="portfolioInfo"
      :loading="loading"
    >
      <p>
        Home Page
      </p>
    </GitHubCard>
    <GitHubCard
      title="Blog2"
      link="https://github.com/kurumiT3/blog2"
      :info="Blog2Info"
      :loading="loading"
    >
      <p>
      My another Blog Site (Theme:fluid)
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
      My BlogInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      portfolioInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      Blog2Info: {
        stargazers_count: 0,
        forks_count: 0,
      },
    }
  },
  mounted() {
    const githubApiUrl = 'https://api.github.com/repos'

    const My Blog = this.axios.get(`${githubApiUrl}/kurumiT3/kurumiT3.github.io`)
    const portfolio = this.axios.get(`${githubApiUrl}/kurumiT3/portfolio`)
    const Blog2 = this.axios.get(`${githubApiUrl}/kurumiT3/blog2`)
    const fatesAxios = this.axios.get(`${githubApiUrl}/SecureCats/Evaluation_BackEnd`)
    const dotfilesAxios = this.axios.get(`${githubApiUrl}/spencerwooo/dotfiles`)

    this.axios
      .all([dowwwAxios, substatsAxios, bithesisAxios, fatesAxios, dotfilesAxios])
      .then(
        this.axios.spread((...resp) => {
          this.loading = false
          this.My BlogInfo= resp[0].data
          this.portfolioInfo = resp[1].data
          this.Blog2Info = resp[2].data
          
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
