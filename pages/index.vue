<template>
  <div class="container">
    <div>
      <header class="content-logos"></header>
      <vs-card>
        <template #title>
          <h3>" {{ quote.affirmation }}..."</h3>
        </template>
        <template #img>
          <img
            v-if="cardBg.urls.regular"
            :src="cardBg.urls.regular"
            loading="lazy"
          />
          <img v-else :src="cardImg" loading="lazy" />
        </template>
        <template #text class="card-bg">
          <span>-Quote Life-</span>
        </template>
      </vs-card>
    </div>
    <div class="create">
      <vs-avatar>
        <img :src="profileUrl" alt="pawaOx4th-profile" loading="lazy" />
      </vs-avatar>
      <p>CREATE BY @PAWAO4TH#</p>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData(ctx) {
    const quote = await ctx.$axios.$get('https://www.affirmations.dev/')
    const cardBg = await ctx.$axios.$get(
      'https://api.unsplash.com/photos/random/?client_id=qId71an2XZyGp5-k44McSHWN465a-xzB3lhIXTu5x7E'
    )

    return {
      quote,
      cardBg,
    }
  },
  data() {
    return {
      quote: '',
      cardBg: {},
      profileUrl:
        'https://firebasestorage.googleapis.com/v0/b/storage-d2584.appspot.com/o/PawaOx4th_Profile.png?alt=media&token=8577e5a8-aed3-423c-a63c-99e8f131a35f',
      cardImg:
        'https://images.unsplash.com/photo-1604785435529-5cfa69e3558f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80',
    }
  },
  head() {
    return {
      title: 'Quote Of Day by PawaOx4th',
      meta: [
        {
          hid: 'Quote Of Day by PawaOx4th',
          name: 'Quote Of Day by PawaOx4th',
          content: 'Home page Quote Of Day by PawaOx4th',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: white;
}

.content-logos {
  margin-bottom: 2rem;
}

.vs-card__text {
  color: #1f9ce4;
}

.create {
  margin-top: 2rem;
  display: flex;
  align-items: center;

  p {
    padding-left: 2rem;
    color: #1a5cff;
    font-weight: bold;
  }
}
</style>
