<template>
  <footer class="page-footer font-small stylish-color-dark pt-4">
    <!-- Footer Links -->
    <div class="container text-center text-md-left">
      <!-- Grid row -->
      <div class="row">
        <!-- Grid column -->
        <div class="col-md-4 mx-auto">
          <!-- Content -->
          <h5 class="font-weight-bold mt-3 mb-4">
            <div>Contact Us</div>
          </h5>

          <ul class="list-unstyled">
            <li v-for="contact in contactDetails" :key="contact.name">
              {{ contact.name }}
              <a :href="contact.link">{{ contact.value }}</a>
            </li>
            <br />
            <li>
              <address>
                Address :
                <br />{{ address }}
              </address>
            </li>
          </ul>
        </div>
        <!-- Grid column -->

        <hr class="clearfix w-100 d-md-none" />

        <!-- Grid column -->
        <div class="col-md-5 mx-auto">
          <!-- Links -->
          <h5 class="font-weight-bold mt-3 mb-4">
            <div>Our Cars</div>
          </h5>

          <ul class="list-unstyled list-inline">
            <li class="list-inline-item" v-for="car in cars" :key="car.name">
              <router-link
                class="linkCars"
                :to="{ name: 'CarModel', params: { carName: car.name } }"
                >{{ car.name }}</router-link
              >
              |
            </li>
          </ul>
        </div>
        <!-- Grid column -->
        <!-- Grid row -->
      </div>
      <!-- Footer Links -->

      <hr />

      <!-- Call to action -->
      <ul class="list-unstyled list-inline text-center py-2">
        <li class="list-inline-item">
          <h5 class="mb-1">Support Us</h5>
        </li>
        <li class="list-inline-item">
          <router-link
            :to="{ name: 'Donation' }"
            class="btn btn-danger btn-rounded"
            >Donate here!</router-link
          >
        </li>
      </ul>
      <!-- Call to action -->

      <hr />

      <!-- Social buttons -->
      <ul class="list-unstyled list-inline text-center" id="social-buttons">
        <li
          class="list-inline-item"
          v-for="(item, index) in Social"
          :key="index"
        >
          <a :href="item.link" target="_blank" class="btn-floating btn-fb mx-1"
            ><img
              :src="require(`@/assets/icons/footer_icons/${item.image}`)"
              alt="fb link"
          /></a>
        </li>
      </ul>
      <!-- Social buttons -->

      <!-- developer -->
      <div class="text-center py-3" id="developer">
        Established by
        <br>
        <a href="https://www.linkedin.com/in/anasmohd/" target="_blank"
          >Mohd Anas</a
        >
        &
        <a
          href="https://www.linkedin.com/in/gauhar-ayub-khan-8202b516b/"
          target="_blank"
          >Gauhar Ayub Khan</a
        >
      </div>
      
      <div class="text-center py-3" id="developer">
        Developers:
        <br>
        <a
          href="https://www.linkedin.com/in/amaan07/"
          target="_blank"
          >Mohd Amaan</a
        >
        &
        <a
          href="https://www.linkedin.com/in/hammad-qamar-96602016b/"
          target="_blank"
          >Hammad Qamar</a
        >

      </div>
      <!-- developer -->
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      contactDetails: [
        {
          name: "Email",
          value: "sae@zhcet.ac.in",
          link: "mailto:sae@zhcet.ac.in"
        },
        {
          name: "Phone No.",
          value: "+918445094080",
          link: "tel:+918445094080"
        }
      ],
      address: "Research & Development center, SAE ZHCET, Mechanical Engineering department,Aligarh Muslim University",
      cars: [
        {
          name: "ZFR 5.0"
        },
        {
          name: "ZFR 4.1"
        },
        {
          name: "ZFR 4.0"
        },
        { name: "ZFR 3.0" },
        {
          name: "ZFR 2.0"
        },
        {
          name: "ZFR 1.0"
        }
      ],
      Social: [
        {
          link: "https://www.facebook.com/ZHCETFormulaRacing/",
          image: "fb.png"
        },
        {
          link: "https://twitter.com/zfr_amu?lang=en",
          image: "twitter.png"
        },
        {
          link:
            "https://www.linkedin.com/company/zhcet-formula-racing-zfr/about/",
          image: "linkedin.png"
        },
        {
          link: "https://www.instagram.com/zhcet_formula_racing/?hl=en",
          image: "insta.png"
        }
      ]
    };
  }
};
</script>
