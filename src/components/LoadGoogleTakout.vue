<script setup>
// import WelcomeItem from "./WelcomeItem.vue";
// import DocumentationIcon from "./icons/IconDocumentation.vue";
// import ToolingIcon from "./icons/IconTooling.vue";
// import EcosystemIcon from "./icons/IconEcosystem.vue";
// import CommunityIcon from "./icons/IconCommunity.vue";
// import SupportIcon from "./icons/IconSupport.vue";
</script>

<template>
  <img src="./assets/googleg_36dp.png" style="max-height: 30px" />
  <q-file
    filled
    v-model="model"
    label="Add watch history export from Google Takout"
    accept=".json,application/json"
  >
    <template v-slot:prepend>
      <q-icon name="cloud_upload" />
    </template>
  </q-file>
</template>
