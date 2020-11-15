<template>
  <div class="container">
    <div class="section">
      <h1>Ratio Image By Netflix</h1>
      <br />
      <hr />
      <br />
      <div class="img--wrapper">
        <img class="image" :src="img169" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Ratio',
  data() {
    return {
      img43:
        'https://images.unsplash.com/photo-1601573189550-fdd602209f1d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2229&q=80',
      img169:
        'https://images.unsplash.com/photo-1565002226877-1d5b69c5d047?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2689&q=80',
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  color: #fff;
  max-width: 80%;
  margin: 0 auto;

  .section {
    margin-top: 2rem;

    .img--wrapper {
      height: 0px;
      padding-bottom: 56.25%;
      position: relative;
      border-radius: 12px;
      overflow: hidden;

      .image {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
