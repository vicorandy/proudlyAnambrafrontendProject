<template>
  <main>
    <downloads></downloads>
    <div class="footer-container">
      <div class="links">
        <div class="link">
          <h5>About Proudly Anambra</h5>
          <ul>
            <li>
              <a href="https://proudlyanambra.com/contact-us">Contact Us</a>
            </li>
            <li><a href="https://proudlyanambra.com/about-us">About Us</a></li>
            <li>
              <a href="https://proudlyanambra.com/terms-and-conditions"
                >Terms & Conditions</a
              >
            </li>
          </ul>
        </div>
        <div class="link">
          <h5>Buyin Products</h5>
          <ul>
            <li><a href="https://proudlyanambra.com/faq">FAQ</a></li>
            <li>
              <a href="https://proudlyanambra.com/return-policy"
                >Return Policy</a
              >
            </li>
            <li>
              <a href="https://proudlyanambra.com/arbitration-policy"
                >Arbitration Policy</a
              >
            </li>
            <li>
              <a href="mailto:contact@proudlyanambra.com">Report Abuse</a>
            </li>
          </ul>
        </div>
        <div class="link">
          <h5>More Links</h5>
          <ul>
            <li>
              <a href="https://proudlyanambra.com/privacy-policy"
                >Privacy Policy</a
              >
            </li>
            <li>
              <a
                href="https://proudlyanambra.com/login?redirect=%2Fspecial-order"
                >Place Special Order</a
              >
            </li>
            <li>
              <a
                href="https://proudlyanambra.com/login?redirect=%2Faccount%2Fdashboard"
                >Become A Seller</a
              >
            </li>
            <li><a href="">Become A Logistic Paetner</a></li>
          </ul>
        </div>
        <div class="link">
          <h5>Stay Connected</h5>
          <ul>
            <li>
              <a href="https://web.facebook.com/ProudlyAnambra/"
                ><i class="pi pi-facebook"></i
              ></a>
            </li>
            <li>
              <a href="https://twitter.com/proudlyanambra"
                ><i class="pi pi-twitter"></i
              ></a>
            </li>
            <li>
              <a href="https://www.instagram.com/proudlyanambra/"
                ><i class="pi pi-instagram"></i
              ></a>
            </li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        <p>2023@FIO Technologies Limited. All Right Resevered</p>
      </div>
    </div>
  </main>
</template>

<script>
import downloads from "./downloads.vue";
import "primeicons/primeicons.css";
export default {
  components: {
    downloads,
  },
};
</script>

<style scoped>
.footer-container {
  background: rgb(85, 84, 84);
  color: aliceblue;
  margin-top: 50px;
}
.links {
  padding: 35px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  justify-items: center;
}
.footer-bottom {
  text-align: center;
  background: rgb(48, 45, 45);
  padding: 2px;
  font-size: 12px;
}
ul {
  margin: 0;
  padding: 0;
}
li {
  list-style: none;
  margin: 0;
}
a {
  margin: 0;
  font-size: 12px;
  text-decoration: none;
  color: aliceblue;
}
h5 {
  margin: 0;
  margin-bottom: 10px;
}
@media only screen and (max-width: 800px) {
  .links {
    grid-template-columns: 1fr 1fr;
  }
  .link {
    margin-top: 20px;
  }
}
</style>
