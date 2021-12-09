<template>
  <div class="experience-parent-class">
    <b-card class="first-class">
      <div class="full-stack-details">
        <h5>
          <b>{{ stack }}</b>
        </h5>
        <ul>
          <li v-for="lang in skillsKnown" :key="lang.id">
            {{ lang.name }}:
            <b-progress animated>
              <b-progress-bar
                :value="lang.value"
                :label="`${lang.value}%`"
              ></b-progress-bar>
            </b-progress>
          </li>
        </ul>
      </div>
    </b-card>
    <b-card>
      <img :src="imageSrc" img-right class="blog-class" />
      <b-card-text>
        {{ blog1 }}
        <div>
          <b>{{ blogDesc }}</b>
        </div>
        {{ wordPress }}
      </b-card-text>
      <b-button :href="paymentBlog" variant="primary" class="button-class">{{
        "View Payment Blog"
      }}</b-button>
      <!-- <hr /> -->
      <!-- <img
        src="data:image/jpeg;base64,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"
        img-right
        class="blog-class"
      />
      <b-card-text>
        <div>
          <b>{{ "Innovate with our APIs" }}</b>
        </div>
        {{
          "Welcome to our API portal where you will find a great selection of APIs for your awesome innovative apps"
        }}
      </b-card-text>
      <b-button
        href="https://developer.yesbank.in/"
        variant="primary"
        class="button-class"
        >{{ "View Payment Blog" }}</b-button
      > -->
    </b-card>
  </div>
</template>

<script>
export default {
  computed: {
    imageSrc() {
      return "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_si2UgaRUuVkdeW3hvQoDmii0VjsAQd_8UQ&usqp=CAU";
    },
    paymentBlog() {
      return "https://www.card91.io/";
    },
  },
  data() {
    return {
      stack: "Front End Stack",
      blog1:
        "Enable New age payment use cases via Card issuance and Management by empowering businesses with payment decisioning and transaction control",
      blogDesc: "Business to Business lending",
      wordPress:
        "is done and this is linked with yes bank ,and we card91 will set the rules for the customer transactions",

      skillsKnown: [
        {
          id: 1,
          name: "Html",
          value: "70",
        },
        {
          id: 2,
          name: "CSS",
          value: "50",
        },
        {
          id: 3,
          name: "Javascript",
          value: "50",
        },
        {
          id: 4,
          name: "Vue Js",
          value: "65",
        },

        {
          id: 5,
          name: "Basics of SQL",
          value: "25",
        },
        {
          id: 6,
          name: "Node Js",
          value: "10",
        },
      ],
      max: 100,
    };
  },
};
</script>

<style>
.first-class {
  height: max-content;
}
.experience-parent-class {
  display: grid;
  grid-template-columns: 0.7fr 1fr;
  grid-column-gap: 30px;
  margin-top: 25px;
}
.blog-class {
  /* width: 174px; */
  padding: 5px 13px 9px 107px;
}
</style>
