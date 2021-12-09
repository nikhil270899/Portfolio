<template>
  <div class="parent-class">
    <b-card class="card-class">
      <div class="details">
        <b-card-img
          :src="require('../assets/nikhilImg.jpg')"
          alt="nikhil profile"
          class="card-img-class"
        ></b-card-img>
        <span class="our-details">
          <span class="detailsClass">
            <span>
              <div class="nameClass">{{ userDetails.name }}</div>
              <div>{{ userDetails.role }}</div>
            </span>
            <span class="cred-class">
              <div>
                <b-icon icon="envelope" class="email-phone-class"></b-icon
                >{{ userDetails.email }}
              </div>
              <div>
                <b-icon icon="telephone-fill" class="email-phone-class">
                </b-icon
                >+91{{ userDetails.phone }}
              </div>
            </span>
          </span>
          <div class="objective-class">
            {{ userDetails.objective1 }}
            <div class="obj-class">
              {{ userDetails.obj1 }}
            </div>
          </div>
        </span>
      </div>
    </b-card>
    <div class="experience-class">
      <Skills />
      <Hobbies />
    </div>
    <div></div>
  </div>
</template>

<script>
import { BIcon } from "bootstrap-vue";
import Skills from "./Skills.vue";
import Hobbies from "./Hobbies.vue";
export default {
  components: {
    "b-icon": BIcon,
    Skills,
    Hobbies,
  },
  data() {
    return {
      userDetails: {
        name: "Kraleti Nikhil",
        role: "Front End Developer",
        email: "nikhil@gmail.com",
        phone: "9939393889",
        objective1:
          "Main objective is to contribute my knowledge and work as a team player,enhance my skills,by that we can delivery the best product.",
        obj1: " I am capable of adapting ,according to the requirement of team and the project & also a keen learner and a good listener.",
      },
    };
  },
};
</script>

<style scoped>
.details {
  display: grid;
  grid-template-columns: 0.42fr 1fr;
}
.cred-class {
  margin-left: 144px;
}
.card-class {
  display: flex;
}
.detailsClass {
  /* margin-right: 40px; */
  display: grid;
  grid-template-columns: 1fr 1.5fr;
}
.card-img-class {
  border-radius: 7px;
  width: 165px;
  margin-left: 18px;
}
.profileDetails {
  padding-right: 5rem;
}
.nameClass {
  font-size: 20px;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 600;
}
.parent-class {
  margin: 30px 256px;
}
.email-phone-class {
  margin-right: 6px;
}
.objective-class {
  margin-top: 36px;
  font-family: emoji;
}
.objective-class > div {
  margin-top: 10px;
}
.experience-class {
  position: relative;
}
</style>
