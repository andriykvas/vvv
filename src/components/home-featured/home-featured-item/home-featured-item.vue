<template name="component-name">
  <li class="featured__item">
    <div class="block__img-wrap">
      <img
        src="https://cloud.squidex.io/api/assets/9a405c69-8e4b-4781-b028-94ad0978ff4a/"
        alt="it`s place for great image"
        class="block__img"
      />
      <div class="block__overlay"></div>
    </div>
    <div class="block__nav">
      <div class="block__date-wrap">
        <time
          :datetime="article.data.date"
          class="block__date date--small date--black "
        >
          {{ article.data.date | formatDate }}
        </time>
      </div>
      <div class="block__link-wrap">
        <router-link
          :to="{
            path: `articles?tag=${_getTag(article.data.tag)}`,
            query: { tag: _getTag(article.data.tag) }
          }"
          class="block__link link--small link--black"
        >
          {{ $t(`label.${_getTag(article.data.tag)}`) }}
        </router-link>
      </div>
    </div>
    <h3 class="featured__title">
      {{ article.data.title }}
    </h3>
    <p class="featured__intro" v-html="article.data.intro"></p>
    <router-link
      :to="'/articles/' + article.data.slug"
      class="block__link link--black"
    >
      {{ $t("global.read-more") }}
    </router-link>
  </li>
</template>

<script>
export default {
  name: "featured-item",
  props: {
    article: {
      type: Object,
      required: true
    }
  }
};
</script>
