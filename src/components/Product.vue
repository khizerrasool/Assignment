<template>
  <div class="product">
    <figure class="productimage">
      <img :src="productImage" />
      <div class="userbox">
        <figure class="round-image">
          <img
            :src="product.influencerImage" />
        </figure>
        <div class="username">
          <h3>{{ product.influencerName }}</h3>
          <span>{{ product.handle }}</span>
        </div>
      </div>
    </figure>
    <div class="datebox">
      <p>
        posted on <span>{{ product.postingDate }}</span>
      </p>
    </div>
    <div class="informationarea">
      <div class="information">
        <strong>{{ product.stats.impressions ?? 0 }}</strong>
        <span>impressions</span>
      </div>
      <div class="information">
        <strong>{{ product.stats.reach ?? 0 }}</strong>
        <span>reach</span>
      </div>
      <div class="information">
        <strong>{{ product.stats.engagement ?? 0 }}%</strong>
        <span>engagement</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    product: {
      images:  Array < String > [],
      influencerName: String,
      influencerImage: { type: String, default: "https://cdn.thecirqle.com/?https://scontent.cdninstagram.com/t51.2885-19/s320x320/57088324_418190442300658_1433682017802780672_n.jpg" },
      handle: String,
      postingDate: String,
      stats: Object < {
        impressions: Number,
        reach: Number,
        engagement: Number
      } > {}
    }
  },
  computed: {
    productImage() {
      return this.product.images.length > 0 ? this.product.images[0] : "https://cdn.filestackcontent.com/6jYNUWIRDaMQND1bJJPl"
    }
  }
};
</script>
