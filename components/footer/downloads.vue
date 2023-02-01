<template>
  <div class="downloads">
    <div class="img">
      <img src="https://proudlyanambra.com/pa-get-app.png" alt="" />
    </div>
    <div class="description">
      <h3>Download our Mobile Application</h3>
      <p>
        To experince more on our platform,click on the button below to download
        our app on your moblie phone platform
      </p>
      <div class="btn-container">
        <button class="btn">
          <a
            href="https://play.google.com/store/apps/details?id=com.archgroup.proudly_anambra&pli=1"
          >
            <img
              src="https://proudlyanambra.com/google-play-badge.png"
              alt=""
            />
          </a>
        </button>
        <button class="btn">
          <a href="https://apps.apple.com/app/proudly-anambra/id6444665068">
            <img
              src="https://proudlyanambra.com/apple-store-badge.png"
              alt=""
            />
          </a>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "downloads",
};
</script>

<style scoped>
.downloads {
  display: flex;
  justify-content: center;
  border-top: 1px solid #d9d9d9;
  padding-top: 20px;
  margin-top: 90px;
}
.description {
  width: 40%;
  padding: 40px;
}
.img {
  height: 350px;
  justify-content: center;
}
.btn {
  height: 45px;
  margin-left: 15px;
  /* width: 40px; */
}

button {
  border-block-style: none;
}
img {
  height: inherit;
  justify-self: center;
}
a {
  text-decoration: none;
  height: 45px;
}
@media only screen and (max-width: 900px) {
  .downloads {
    flex-direction: column;
    margin-left: auto;
    margin-right: auto;
    width: 90%;
  }
  .img {
    display: flex;
  }
  .description {
    width: 80%;
    justify-content: center;
    margin: 0 auto;
  }
}
@media only screen and (max-width: 500px) {
  .img {
    height: 300px;
  }
}
</style>
