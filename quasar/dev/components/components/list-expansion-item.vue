<template>
  <div class="bg-white">
    <div class="q-layout-padding q-mx-auto" style="max-width: 600px;">
      <p class="caption">Explore the possibilities</p>
      <q-list bordered padding>
        <q-expansion-item
          v-model="open"
          expand-separator
          icon="perm_identity"
          label="With a model and events"
        >
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-item>
          <q-item-section avatar>
            <q-icon name="signal_wifi_off" />
          </q-item-section>

          <q-item-section>
            Regular item
          </q-item-section>
        </q-item>

        <q-expansion-item expand-separator icon="shopping_cart" label="Toggle by right-side icon only" expand-icon-toggle>
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item header-inset expand-separator label="With header inset">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item content-inset expand-separator icon="map" label="With content inset">
          <div class="q-py-md q-pr-md">
            {{ lorem }}
          </div>
        </q-expansion-item>

        <q-expansion-item expand-separator icon="explore" label="With right-side icon too">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item expand-separator>
          <template slot="header">
            <q-item-section avatar>
              <q-avatar icon="bluetooth" color="primary" text-color="white" />
            </q-item-section>

            <q-item-section>
              <div>
                <q-chip color="secondary" text-color="white" class="q-mr-sm">
                  Using slot
                </q-chip>
              </div>
            </q-item-section>

            <q-item-section side>
              <div class="row items-center">
                <q-icon name="star" color="red" size="24px" />
                <q-icon name="star" color="red" size="24px" />
                <q-icon name="star" color="red" size="24px" />
              </div>
            </q-item-section>
          </template>

          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item expand-separator>
          <template slot="header">
            <q-item-section avatar>
              <q-avatar>
                <img src="statics/boy-avatar.png">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              With Avatar
            </q-item-section>
          </template>

          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item icon="drafts" label="Disabled" disable>
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item expand-separator label="Jim">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item expand-separator dense label="Dense" icon="settings">
          <div class="q-pa-sm">
            {{ lorem }}
          </div>
        </q-expansion-item>
      </q-list>

      <p class="caption">Links</p>
      <q-list bordered>
        <q-expansion-item expand-separator to="/" exact icon="home" label="Inactive link">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item expand-separator :to="$route.path" icon="home" label="Active link">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <!-- check .my-expand-link CSS class below -->
        <q-expansion-item
          expand-separator
          :to="$route.path"
          active-class="my-expand-link"
          icon="home"
          label="Customized active link"
        >
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </q-list>

      <p class="caption">Make use of events</p>
      <q-expansion-item class="shadow-1" style="border-radius: 30px" icon="explore" label="Counter" @show="startCounting" @hide="stopCounting">
        <q-card>
          <q-card-section>
            Counting: <q-chip dense color="secondary" text-color="white">{{ counter }}</q-chip>
            Will only count when opened, using the show/hide events to control count timer.
          </q-card-section>
        </q-card>
      </q-expansion-item>

      <p class="caption">On dark Background</p>
      <q-expansion-item dark class="bg-black" icon="shopping_cart" label="Toggle me">
        <q-card dark class="bg-black">
          <q-card-section>
            {{ lorem }}
          </q-card-section>
        </q-card>
      </q-expansion-item>

      <p class="caption">Multiline</p>
      <q-list bordered inset-separator>
        <q-expansion-item icon="mail" label="Inbox" caption="5 unread emails">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
        <q-expansion-item icon="send" label="Outbox" caption="Empty">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </q-list>

      <p class="caption">Switch toggle side</p>
      <q-list bordered padding inset-separator>
        <q-expansion-item switch-toggle-side icon="mail" label="Inbox" caption="5 unread emails">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
        <q-expansion-item switch-toggle-side icon="send" label="Outbox" caption="Empty">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
        <q-separator />
        <q-expansion-item switch-toggle-side dense-toggle icon="mail" label="Inbox" caption="5 unread emails">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
        <q-expansion-item switch-toggle-side dense-toggle icon="mail" label="Inbox" caption="5 unread emails">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </q-list>

      <p class="caption">Popups</p>
      <div>
        <q-expansion-item popup icon="mail" label="Inbox" caption="5 unread emails">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
        <q-expansion-item popup icon="send" label="Outbox" caption="Empty">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
        <q-expansion-item popup icon="drafts" label="Draft" caption="Draft a new email">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </div>

      <p class="caption">Menu</p>
      <q-list bordered>
        <q-expansion-item expand-separator icon="mail" label="Inbox" :content-inset-level="1" caption="5 unread emails" default-opened>
          <q-expansion-item expand-separator icon="receipt" label="Receipts">

            <q-expansion-item label="Today" :header-inset-level="1" :content-inset-level="1">
              <q-card>
                <q-card-section>
                  {{ lorem }}
                </q-card-section>
              </q-card>
            </q-expansion-item>

            <q-expansion-item label="Yesterday" :header-inset-level="1" :content-inset-level="1">
              <q-card>
                <q-card-section>
                  {{ lorem }}
                </q-card-section>
              </q-card>
            </q-expansion-item>

          </q-expansion-item>

          <q-expansion-item expand-separator icon="schedule" label="Postponed">
            <q-card>
              <q-card-section>
                {{ lorem }}
              </q-card-section>
            </q-card>
          </q-expansion-item>

        </q-expansion-item>

        <q-expansion-item expand-separator icon="mail" label="Inbox" caption="5 unread emails" default-opened>
          <q-expansion-item expand-separator :header-inset-level="1" icon="receipt" label="Receipts">

            <q-expansion-item label="Today" :header-inset-level="2" :content-inset-level="2">
              <q-card>
                <q-card-section>
                  {{ lorem }}
                </q-card-section>
              </q-card>
            </q-expansion-item>

            <q-expansion-item label="Yesterday" :header-inset-level="2" :content-inset-level="2">
              <q-card>
                <q-card-section>
                  {{ lorem }}
                </q-card-section>
              </q-card>
            </q-expansion-item>

          </q-expansion-item>

          <q-expansion-item expand-separator :header-inset-level="1" :content-inset-level="2" icon="schedule" label="Postponed">
            <q-card>
              <q-card-section>
                {{ lorem }}
              </q-card-section>
            </q-card>
          </q-expansion-item>

        </q-expansion-item>

        <q-expansion-item expand-separator label="Inbox" caption="5 unread emails" :content-inset-level="0.5" default-opened>
          <q-expansion-item expand-separator label="Receipts">

            <q-expansion-item label="Today" :header-inset-level="0.5" :content-inset-level="0.5">
              <q-card>
                <q-card-section>
                  {{ lorem }}
                </q-card-section>
              </q-card>
            </q-expansion-item>

            <q-expansion-item label="Yesterday" :header-inset-level="0.5" :content-inset-level="0.5">
              <q-card>
                <q-card-section>
                  {{ lorem }}
                </q-card-section>
              </q-card>
            </q-expansion-item>

          </q-expansion-item>

          <q-expansion-item expand-separator :content-inset-level="0.5" label="Postponed">
            <q-card>
              <q-card-section>
                {{ lorem }}
              </q-card-section>
            </q-card>
          </q-expansion-item>

        </q-expansion-item>

        <q-expansion-item expand-separator icon="send" label="Outbox" caption="Empty">
          <q-expansion-item label="Today" :header-inset-level="1" :content-inset-level="1">
            <q-card>
              <q-card-section>
                {{ lorem }}
              </q-card-section>
            </q-card>
          </q-expansion-item>

          <q-expansion-item label="Yesterday" :header-inset-level="1" :content-inset-level="1">
            <q-card>
              <q-card-section>
                {{ lorem }}
              </q-card-section>
            </q-card>
          </q-expansion-item>
        </q-expansion-item>

        <q-expansion-item expand-separator :content-inset-level="1" icon="drafts" label="Draft" caption="Draft a new email">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </q-list>

      <p class="caption">Group a.k.a Accordion (opening one closes the other)</p>
      <q-list bordered>
        <q-expansion-item group="somegroup" icon="explore" label="First" default-opened>
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-separator />

        <q-expansion-item group="somegroup" icon="perm_identity" label="Second" header-class="text-red">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-separator />

        <q-expansion-item group="somegroup" icon="shopping_cart" label="Third" header-class="text-primary">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-separator />

        <q-expansion-item group="somegroup" icon="bluetooth" label="Fourth">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </q-list>

      <p class="caption">Preselected/Opened Collapsible (or use a model)</p>
      <q-list bordered separator>
        <q-expansion-item icon="explore" label="First">
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item icon="perm_identity" label="Second" default-opened>
          <q-card>
            <q-card-section>
              {{ lorem }}
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </q-list>

      <p class="caption">Ubiquity. Using Cards as content.</p>
      <q-list bordered class="q-pa-none">
        <q-expansion-item icon="explore" label="First Card">
          <q-card class="bg-grey-3">
            <q-card-section>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dicta vero vitae consequatur, id commodi magnam deleniti voluptas, alias, numquam labore maiores sit a dolores aliquid molestias veritatis nulla. Deleniti, debitis?
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-separator />

        <q-expansion-item icon="explore" label="Second Card">
          <q-card class="bg-grey-3">
            <q-card-section>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dicta vero vitae consequatur, id commodi magnam deleniti voluptas, alias, numquam labore maiores sit a dolores aliquid molestias veritatis nulla. Deleniti, debitis?
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-separator />

        <q-expansion-item icon="explore" label="Third Card">
          <q-card class="bg-grey-3">
            <q-card-section>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dicta vero vitae consequatur, id commodi magnam deleniti voluptas, alias, numquam labore maiores sit a dolores aliquid molestias veritatis nulla. Deleniti, debitis?
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-separator />

        <q-expansion-item icon="shopping_cart" label="Fourth Card">
          <q-card class="q-ma-md" flat>
            <img src="~assets/map.png">

            <q-list>
              <q-item clickable>
                <q-item-section avatar>
                  <q-icon color="primary" name="local_bar" />
                </q-item-section>

                <q-item-section>
                  <q-item-label>Bar XYZ</q-item-label>
                  <q-item-label caption>Have a drink.</q-item-label>
                </q-item-section>
              </q-item>

              <q-item clickable>
                <q-item-section avatar>
                  <q-icon color="red" name="local_gas_station" />
                </q-item-section>

                <q-item-section>
                  <q-item-label>Gas Station</q-item-label>
                  <q-item-label caption>Fill your gas tank.</q-item-label>
                </q-item-section>
              </q-item>

              <q-item clickable>
                <q-item-section avatar>
                  <q-icon color="amber" name="local_movies" />
                </q-item-section>

                <q-item-section>
                  <q-item-label>Cinema XYZ</q-item-label>
                  <q-item-label caption>Watch a movie.</q-item-label>
                </q-item-section>
              </q-item>
            </q-list>

            <q-card-actions class="items-center">
              <div class="text-body2 text-primary">
                13 minutes
              </div>
              <div class="text-body2 q-pl-sm">
                (1 mile)
              </div>
              <q-space />
              <q-btn flat color="primary" icon="directions" label="Start" />
            </q-card-actions>
          </q-card>
        </q-expansion-item>
      </q-list>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      open: false,
      counter: 0,
      lorem: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempore, nemo minus dolore facere saepe molestias, fugiat officia aspernatur expedita pariatur, accusantium hic exercitationem perspiciatis voluptate possimus nobis temporibus ipsa officiis!'
    }
  },
  methods: {
    notify (message, close) {
      this.$q.notify({
        color: close ? 'tertiary' : 'secondary',
        message
      })
    },
    startCounting () {
      console.log('counter start')

      this.hndl = setInterval(() => {
        this.counter++
      }, 1000)
    },
    stopCounting () {
      console.log('counter stop')

      clearInterval(this.hndl)
    }
  }
}
</script>

<style lang="stylus">
@import '~quasar-variables'

.my-expand-link
  color $secondary
  background alpha($secondary, .1)
  .q-item__section--side .q-icon
    color $secondary
</style>
