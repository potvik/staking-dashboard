<template>
  <SessionFrame>
    <div id="session-welcome">
      <router-link to="/">
        <img
          class="session-logo-mobile"
          src="~assets/images/harmony-logo-white.svg"
          alt="a small spinning circle to display loading"
        />
      </router-link>

      <h2 class="session-title">
        Welcome to Harmony
      </h2>

      <p class="session-paragraph">
        The easiest way to send, stake, and vote on the One Blockchain.
      </p>

      <div class="session-list">
        <LiSession
          id="creat-new-address"
          icon="person_add"
          title="Create a new address"
          :route="extension.enabled ? 'extension' : 'create'"
        />
        <LiSession
          id="use-an-existing-address"
          icon="person"
          title="Use an existing address"
          route="existing"
        />
      </div>

      <p class="footnote">
        By using Harmony, you accept our
        <router-link to="/terms" class="link">
          Terms of Service
        </router-link>
        and
        <router-link to="/privacy" class="link"> Privacy Policy </router-link>.
      </p>
    </div>
  </SessionFrame>
</template>

<script>
import SessionFrame from "common/SessionFrame.vue"
import LiSession from "common/TmLiSession"
import { mapState } from "vuex"

export default {
  name: `session-welcome`,
  components: {
    SessionFrame,
    LiSession
  },
  computed: {
    ...mapState([`extension`])
  }
}
</script>
<style scoped>
.session-title {
  padding: 0 1rem;
}
</style>
