<template>
  <div class="project-class">
    <h4 class="title-class">Projects({{ projects.length }})<b></b></h4>
    <b-tabs pills card>
      <b-tab
        v-for="project in projects"
        :key="project.id"
        :title="project.lang"
        :active-tab-class="project.id"
        ><b-card-text class="tex-class"
          ><div class="mt-2">
            <b>{{ project.name }}</b>
          </div>
          <div class="mt-2">{{ project.desc }}</div>
        </b-card-text></b-tab
      >
    </b-tabs>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          id: 1,
          name: "Card91 issuance",
          lang: "Vue",
          desc: "Basically this is a issuance based project ,linked with yes bank we as card91 will issue the card to customers with txn rules and payment will be authenticated via yes bank ",
        },
        {
          id: 2,
          name: "Portfolio",
          lang: "Html,css",
          desc: "Made using html,css,js,vue",
        },
      ],
    };
  },
};
</script>

<style>
.project-class {
  padding: 30px;
}
.tex-class {
  padding-top: 1rem;
}
</style>
