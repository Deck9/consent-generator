<template>
  <form>
    <!-- Start Generic Form here -->
    <PanelHeader
      title="General Information"
      description="You need to provide this information, to make it easy for others find out more about you or to contact you."
    />

    <div class="mt-6 grid grid-cols-1 row-gap-6 col-gap-4 sm:grid-cols-6">
      <div class="sm:col-span-4">
        <label
          for="company"
          class="block text-sm font-medium leading-5 text-gray-700"
        >
          Your company name
        </label>
        <div class="mt-1 rounded-md shadow-sm">
          <input
            id="company"
            type="text"
            :value="company"
            class="form-input block w-full transition duration-150 ease-in-out sm:text-sm sm:leading-5"
            @change="setCompany($event.target.value)"
          />
        </div>
      </div>

      <div class="sm:col-span-3">
        <label
          for="name"
          class="block text-sm font-medium leading-5 text-gray-700"
        >
          Contact Person
        </label>
        <div class="mt-1 rounded-md shadow-sm">
          <input
            id="name"
            :value="name"
            class="form-input block w-full transition duration-150 ease-in-out sm:text-sm sm:leading-5"
            @change="setName($event.target.value)"
          />
        </div>
      </div>

      <div class="sm:col-span-3">
        <label
          for="email"
          class="block text-sm font-medium leading-5 text-gray-700"
        >
          Contact Email
        </label>
        <div class="mt-1 rounded-md shadow-sm">
          <input
            id="email"
            type="email"
            :value="email"
            class="form-input block w-full transition duration-150 ease-in-out sm:text-sm sm:leading-5"
            @change="setEmail($event.target.value)"
          />
        </div>
      </div>

      <div class="sm:col-span-4">
        <label
          for="privacy-url"
          class="block text-sm font-medium leading-5 text-gray-700"
        >
          Privacy Policy
        </label>
        <div class="mt-1 rounded-md shadow-sm">
          <input
            id="privacy-url"
            type="url"
            :value="privacy_url"
            class="form-input block w-full transition duration-150 ease-in-out sm:text-sm sm:leading-5"
            @change="setPrivacyUrl($event.target.value)"
          />
        </div>
      </div>

      <div class="sm:col-span-4">
        <label
          for="legal-notice"
          class="block text-sm font-medium leading-5 text-gray-700"
        >
          Legal Notice
        </label>
        <div class="mt-1 rounded-md shadow-sm">
          <input
            id="legal-notice"
            type="url"
            :value="legal_notice_url"
            class="form-input block w-full transition duration-150 ease-in-out sm:text-sm sm:leading-5"
            @change="setLegalNoticeUrl($event.target.value)"
          />
        </div>
      </div>
    </div>
    <!-- End Generic Form -->
  </form>
</template>

<script>
import { mapState, mapMutations } from "vuex";
import PanelHeader from "./partials/PanelHeader";

export default {
  components: {
    PanelHeader
  },

  computed: {
    ...mapState(["company", "name", "email", "privacy_url", "legal_notice_url"])
  },

  methods: {
    ...mapMutations([
      "setCompany",
      "setName",
      "setEmail",
      "setPrivacyUrl",
      "setLegalNoticeUrl"
    ])
  }
};
</script>
