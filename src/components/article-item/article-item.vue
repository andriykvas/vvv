<template>
  <li class="block__item">
    <div class="block__img-wrap">
      <img
        src= "https://cloud.squidex.io/api/assets/1690567f-cebd-43d7-a668-83eff0b7736e/"
        alt="article-image"
        class="block__img"
      />
      <div class="block__overlay"></div>
    </div>
    <div class="block__nav">
      <div class="block__date-wrap">
        <time
          :datetime="data.date"
          class="block__date date--small date--black "
        >
          {{ data.date | formatDate }}
        </time>
      </div>
      <div class="block__link-wrap">
        <router-link
          :to="{
            path: `articles?tag=${_getTag(data.tag)}`,
            query: { tag: _getTag(data.tag) }
          }"
          class="block__link link--small link--black"
        >
          {{ $t(`label.${_getTag(data.tag)}`) }}
        </router-link>
      </div>
    </div>
    <h2 class="block__title">{{ data.title }}</h2>
    <router-link :to="'/articles/' + data.slug" class="block__link link--black">
      {{ $t("global.read-more") }}
    </router-link>
  </li>
</template>

<script>
export default {
  name: "article-item",
  props: {
    data: {
      type: Object,
      required: true
    }
  }
};
</script>
