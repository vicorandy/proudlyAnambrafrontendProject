<template>
  <feature-carousel :slides="slides"></feature-carousel>
</template>

<script>
import FeatureCarousel from "./FeatureCarousel.vue";
export default {
  name: "FeaturecarouselSlide",
  transitions: "slide-in",
  components: {
    FeatureCarousel,
  },
  data() {
    return {
      slides: [
        "https://s3-alpha-sig.figma.com/img/e94d/0cc4/5e5c44923bb204f2b2e20358b966ddb9?Expires=1675036800&Signature=cKH55t0tC6vk6NXENP~yqKbuJEOYiA~YhSe87-GMrluXDT7g3ydg7s9oFl4eCFE80mUAktdKFOEFwvhwwynBCUA58Xjbn5yCK8wa56xZihlOKqzW8srU5dJK-OzgmSJr9-W~x0cq8mOXDr0BBjOPxzvzMzwnGi2NOnHbxrG1OFH-XE8lahWlYNdSRJltR4vO1ekxw-4sjnKHoij-lvAR2WKQayFwVoMbrY-Kfxxrn9~dWmzguxWU1IMXaR5v-jFEb3nbXrFaEH3zRp03YZkYBxMVFRvIx2rb8DKQGRPo1ZsqKbAqX37~hp0l-BtVUZ9FG~AJUXZhLV9Vr98NVQxUeQ__&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4",
        "https://picsum.photos/id/1032/1096/368",
        "https://picsum.photos/id/1033/1096/368",
        "https://picsum.photos/id/1036/1096/368",
      ],
    };
  },
};
</script>

<style></style>
