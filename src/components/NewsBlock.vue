<template>
  <div>
    <b-card
      :title="news_block.title"
      :img-src="news_block.urlToImage"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem"
      class="mb-2"
    >
      <b-card-text>
        {{ news_block.description }}
      </b-card-text>

      <b-button href="#" variant="primary">Read More</b-button>
    </b-card>
  </div>
</template>


<script>
export default {
  props: {
    news_block: Object
  }
};
</script>
