<template>
  <section class="home-baner">
    <div class="baner__wrap">
      <div class="baner__img-box">
        <img
          class="baner__img"
          alt="image of baner"
          src="https://cloud.squidex.io/api/assets/d2da0b2d-29aa-485b-8cda-9ded0ec7ef50/"
        />
      </div>

      <BanerArticle :banerArticle="articlesByTag" />
    </div>
  </section>
</template>

<script>
export default {
  name: "home-baner",
  props: {
    tag: {
      type: Object,
      required: true
    }
  },

  computed: {
    articlesByTag() {
      const articles = this.$store.state.blog.articlesHome[this.tag.data.title];
      return articles[0];
    }
  }
};
</script>

<style lang="scss">
@import "home-baner.scss";
</style>
