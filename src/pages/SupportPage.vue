<template>
  <div class="page">
    <header-section showNavSearch="true" />
    <main role="main" class="section margin-bottom-large">
      <div class="container is-fluid">
        <div class="margin-bottom-large">
          <h1 class="title is-2 margin-bottom-normal">
            {{ $t('support.title') }}
          </h1>
          <div class="margin-bottom-normal">
            <article
              class="card entry-post entry-image horizontal column is-half is-offset-one-quarter"
            >
              <header class="card-image">
                <figure class="image">
                  <img src="../assets/support.png" alt="Header image" />
                </figure>
              </header>
              <div class="card-content with-button">
                <div class="content">
                  <h2>CC Search</h2>
                  <span
                    class="subtitle is-italic margin-bottom-normal is-uppercase"
                  >
                    {{ $t('support.open') }}</span
                  >
                  <p>
                    {{ $t('support.cc') }}
                  </p>
                </div>
                <a
                  class="button normal donate margin-right-normal"
                  @click="sendDonationEvent"
                  :href="donationLink"
                >
                  <i
                    class="icon cc-letterheart-filled margin-right-small padding-top-smaller"
                  ></i>
                  {{ $t('support.button.donate') }}</a
                >
              </div>
            </article>
            <i18n
              path="support.quote"
              tag="p"
              class="has-text-centered is-uppercase"
            >
              <template v-slot:joy>
                <a
                  aria-label="licenses"
                  href="https://www.flickr.com/photos/33363480@N05/14084531185"
                  >"Joy is the simplest form of gratitude... Karl Barth"</a
                >
              </template>
              <template v-slot:writer>
                <a
                  aria-label="public domain"
                  href="https://www.flickr.com/photos/33363480@N05"
                  >Nick Kenrick.</a
                >
              </template>
              <template v-slot:cc>
                <a
                  aria-label="photograph"
                  href="https://creativecommons.org/licenses/by/2.0/?ref=ccsearch&atype=rich"
                  >CC BY 2.0
                </a>
              </template>
            </i18n>
          </div>
          <p class="margin-bottom-normal">{{ $t('support.inclusive') }}</p>
          <i18n path="support.work" tag="p" class="margin-bottom-normal">
            <template v-slot:license>
              <a
                aria-label="licenses"
                href="https://creativecommons.org/licenses/"
                >CC License Suite</a
              >
            </template>
            <template v-slot:public-domain>
              <a
                aria-label="public domain"
                href="https://creativecommons.org/publicdomain/"
                >public domain tools</a
              >
            </template>
            <template v-slot:photograph>
              <a
                aria-label="photograph"
                href="https://www.parismuseescollections.paris.fr/fr/musee-carnavalet/oeuvres/portrait-de-l-ecrivaine-libertaire-et-feministe-caroline-remy-dite-severine"
                >this photograph</a
              >
            </template>
            <template v-slot:guide>
              <a
                aria-label="guide"
                href="https://pressbooks.library.ryerson.ca/docs/"
                >this guide</a
              >
            </template>
          </i18n>
          <h2 class="title subtitle is-3 margin-bottom-normal">
            {{ $t('support.free') }}
          </h2>
          <p class="margin-bottom-normal">{{ $t('support.access') }}</p>
          <i18n path="support.public-good" tag="p" class="margin-bottom-normal">
            <template v-slot:public-good>
              <strong>public good</strong>
            </template>
          </i18n>
          <div class="field button-row">
            <a
              @click="sendDonationEvent"
              class="button normal donate"
              :href="donationLink"
            >
              <i
                class="icon cc-letterheart-filled margin-right-small padding-top-smaller"
              ></i>
              {{ $t('support.button.donate') }}</a
            >
            <h2 class="title subtitle is-3 seperator">or</h2>
            <a
              class="button is-primary normal"
              href=" https://github.com/sponsors/creativecommons"
              >{{ $t('support.button.sponsor') }}</a
            >
          </div>
          <h2 class="title subtitle is-3 margin-vertical-normal">
            {{ $t('support.launch.title') }}
          </h2>
          <p class="margin-bottom-normal">{{ $t('support.launch.first') }}</p>
          <div class="content">
            <ul>
              <li>
                {{ $t('support.launch.served') }}
              </li>
              <li>
                {{ $t('support.launch.host') }}
              </li>
              <li>
                {{ $t('support.launch.users') }}
              </li>
              <li>
                {{ $t('support.launch.visitors') }}
              </li>
            </ul>
          </div>
          <strong
            ><p class="margin-bottom-normal">
              {{ $t('support.launch.education') }}
            </p></strong
          >
          <h2 class="title subtitle is-3 margin-bottom-normal">
            {{ $t('support.future.title') }}
          </h2>
          <p class="margin-bottom-normal">{{ $t('support.future.more') }}</p>
          <div class="content">
            <ul>
              <li>
                {{ $t('support.future.culture') }}
              </li>
              <li>
                {{ $t('support.future.audio') }}
              </li>
              <li>
                {{ $t('support.future.video') }}
              </li>
              <li>
                {{ $t('support.future.text') }}
              </li>
              <li>
                {{ $t('support.future.internalize') }}
              </li>
              <li>
                {{ $t('support.future.translate') }}
              </li>
              <li>
                {{ $t('support.future.accessibility') }}
              </li>
              <li>
                {{ $t('support.future.smarter') }}
              </li>
            </ul>
          </div>
          <h2
            class="title subtitle is-3 margin-bottom-normal has-text-centered"
          >
            {{ $t('support.future.support') }}
          </h2>
          <div class="field button-row margin-bottom-medium">
            <a
              class="button normal donate"
              @click="sendDonationEvent"
              :href="donationLink"
            >
              <i
                class="icon cc-letterheart-filled margin-right-small padding-top-smaller"
              ></i>
              {{ $t('support.button.donate') }}</a
            >
          </div>
          <p class="margin-bottom-normal">{{ $t('support.grateful') }}</p>
        </div>
      </div>
    </main>
    <footer-section />
  </div>
</template>

<script>
import HeaderSection from '@/components/HeaderSection'
import FooterSection from '@/components/FooterSection'
import ServerPrefetchProvidersMixin from '@/pages/mixins/ServerPrefetchProvidersMixin'
import GoogleAnalytics from '@/analytics/GoogleAnalytics'
import { DonateLinkClick } from '@/analytics/events'

const MetaSearchPage = {
  name: 'meta-search-page',
  mixins: [ServerPrefetchProvidersMixin],
  components: {
    HeaderSection,
    FooterSection,
  },
  data() {
    return {
      donationLink: 'https://www.classy.org/give/297881/#!/donation/checkout',
    }
  },
  methods: {
    sendDonationEvent() {
      GoogleAnalytics().sendEvent(DonateLinkClick('support-page'))
    },
  },
}

export default MetaSearchPage
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import 'bulma/sass/utilities/_all.sass';
@import '@/styles/text-only-page.scss';

h4 {
  margin: 1rem 0;
}

.button-row {
  display: flex;
  align-items: center;
  justify-content: center;

  .seperator {
    margin: 0 1.5rem;
  }

  @include touch {
    flex-direction: column;

    .seperator {
      margin: 0.5rem;
    }
  }
}
</style>
