<template>
  <carousel :slides="slides"></carousel>
</template>

<script>
import Carousel from "./Carousel.vue";
export default {
  name: "CarouselSlide",
  transitions: "slide-in",
  components: {
    Carousel,
  },
  data() {
    return {
      slides: [
        "https://s3-alpha-sig.figma.com/img/f6f7/4326/af6dfd833d76e546a70e520c55b2d24d?Expires=1676246400&Signature=nStza1xvr66oTSfsTRlZSer2SIvKc1luQhk~ecTrFgtbRNYWOshWTIIettLuXvoJG46EmqSyQYg8TgzKTq-ZcCTseqepVDodFZ2eNnzAHB34he~3kAObE6KHx0NymjZMK~K3bw5N1kouOuTRAspfTIZ2IVM3AAkZ5YJNUhkmoBBG6kDBKdLc3hgZtqsc3ukpJyY0ONrDca720RQ3JVnwH2PTafDnrOzKPLVQyMPzqoL7NB0js-O0tKab1qkQ4nHL5koSy1UqRofLjiwWnFb1iDVG0qmmv5hPQ7G3L6BEZJ8d2D0dkmiXHpYlyrnSDQUIW-BO94MEz5ClnJQx9jgH1Q__&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4",
        "https://s3-alpha-sig.figma.com/img/9136/2799/020fe69eb483e21a018a8e07cb1b02d9?Expires=1676246400&Signature=apuou0d9pQN7eRroyZzf6dBEMQ105B8yRR01FuZ-CJzj4q83L3gKTSojQEJWOPXIVqSBuaM9LROajeqNiAO4eGY6I8meuzRcpCRQs0jSE-Sxm0wuhPKVmbjpHAbcUR6lvDeVfk4Ud9p0~fj6nKFknDLUKTi1X3OyypaKBk4C0vz6szLDm5g7yP8jrIcEzBFo02Rrx5Za93ma4dSQRIm-uIHVHtWF6g7cJRl5xfUt~xo81Ne1ixzepUU5k6bWzkujgSXT-W-GPf84eAo2KlmwSgEV1ut0eOwYvKEoJt1d2~OHwGuI~y4E9IPM~5Ehpaocvbj6kXbr4J3QV4iFSKYRcA__&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4",
        "https://s3-alpha-sig.figma.com/img/cfc4/cbbf/8a8dbc00f845b94d5fea6d6c0034a532?Expires=1676246400&Signature=TahHoVg9BLweLiYdRmVyHt5iGEz9EtbXNgpG4TfbL6tblePJiYXP1ZC2M7K0MwgneFa7OTolQ2jd9sitHdT2JLkufRhd5QT0xJV~H59Q2LlDqI4xlS1oycGnYEMEGNSRlrrHS-mKhwmRYEHtWpkpkvse4Kj2i06XmGhsGDyI4JaOS9Do7Abkd7jugVeW~EPVP2hLGmVBe9gB2kpgDS1zbrpZ4UHsphTykNBag98axu6qE02Y3uXk9PpJBP0NfLZC5WHh3vlzDVPbQOoXpFjOZbKrJdNHp8ZSi1OohTSV9HJyYlR9eQCfA1q4rs9JXPWnfW~7wTRBEsrO9CltI4mTbg__&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4",
        "https://s3-alpha-sig.figma.com/img/d4bd/d068/6acd1e4834b51093d2a354ef895c6f55?Expires=1676246400&Signature=F3G6T8-WFWATE3EnMsYTE8vRGkURMZ6jy9EyK~cdmpNyUfXCn4ZVigsLZoygM6vwqZG6QgWiOpf-3PibNNsloghRdeQS1ERufVCdgsbsRvlfnz6J8PYK8DFpX26eJE5ir5MTVDkJ7YYlQb9VSYmUrtZ5FARArdKgl8l00IWy7cErWihsza4TRRKyXkcz3R~LupuWPWLXmi0tsOlTn2ImDUK0CGehGPgauYy6BRqtiZzFVQKhg0i-S2SXYDk3HZZWltLmfZHIJWEvuQ~T8PAjpVgdfSnVAbaNLybUOgwaSw3VUHNx8FgXI0fi1XyPne648WXR6sgB3Yna5EUnV7617Q__&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4",
        "https://s3-alpha-sig.figma.com/img/7b23/7bb4/2b18ef4c968431b4db3b1ea12adbafed?Expires=1676246400&Signature=b-fX1K9u59Ybpdgp7XH4WhZjfzzJIRb70P00zLMaTcWUZWhbm~AHhZj~AJid1zU4C4OP3M~TKgol3vggjw6k9nwCag4RUocY7cLVoNKIgl-1F-3~ps4l5cZ4C~w4M17ZHaQ6X91ExVn-iPH09HB8STVlFAXaVY1jE9CQXUnElMbdn01IRk0TRxAtiCV2qfP2RSCPuqzWltu0iTTSgx7ds8ZAqNQUzEY8TCRlgIpJf7XHC3OljJSRAemaXcUdFIBdmUKQVUa1XcU6iSI~UalR-p6iFzSA2Bh5snxr-fwDvicVoxM2eD4g-3oEv9vP0gaZZbMj3Gfh47Ss8iwVKXrlFQ__&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4",
      ],
    };
  },
};
</script>

<style></style>
