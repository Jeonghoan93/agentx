<script setup lang="ts">
import { useDisplay } from 'vuetify'

const milestones = [
  {
    title: 'MVP Launch',
    timeframe: 'Month 1-2',
    description: 'Launch livestream platform for festivals and events'
  },
  {
    title: 'First Major Festival Partnership',
    timeframe: 'Month 3',
    description:
      'Secure and implement first major festival livestream partnership'
  },
  {
    title: 'User Acquisition',
    timeframe: 'Month 3-6',
    description: 'Reach 10,000 active users through livestream events'
  },
  {
    title: 'VR Feature Development',
    timeframe: 'Month 4-8',
    description:
      'Develop and test core VR functionality for immersive experiences'
  },
  {
    title: 'Custom Events Feature',
    timeframe: 'Month 8-12',
    description: 'Launch platform for users to create custom VR events'
  },
  {
    title: 'Series A Preparation',
    timeframe: 'Month 10-12',
    description: 'Prepare metrics and growth data for Series A fundraising'
  }
]

const expandedIndex = ref<number | null>(null)

const toggleExpand = (index: number) => {
  if (expandedIndex.value === index) {
    // If clicking the currently expanded item, close it
    expandedIndex.value = null
  } else {
    // Otherwise, open the clicked item (and implicitly close any other)
    expandedIndex.value = index
  }
}

const fundUsage = ref([
  {
    category: 'VR Development',
    percentage: 50,
    description:
      'Core engineering team and technology development for immersive VR experiences'
  },
  {
    category: 'Marketing & Partnerships',
    percentage: 30,
    description:
      'Festival partnerships, user acquisition, and community building'
  },
  {
    category: 'Operations',
    percentage: 10,
    description:
      'Day-to-day operations, cloud infrastructure, and team management'
  },
  {
    category: 'Legal & Compliance',
    percentage: 10,
    description:
      'Legal structure, agreements with PartyX, and regulatory compliance'
  }
])

const { xs } = useDisplay()
</script>

<template>
  <Navbar />

  <v-container class="bg-gray-6 mt-[60px] flex flex-col gap-10">
    <!-- Hero Section -->
    <section class="py-10">
      <v-row justify="center" align="center">
        <v-col cols="12" md="10" class="text-center">
          <h1 class="text-gradient text-h3 font-weight-bold mb-6">
            Experience Events in Virtual Reality
          </h1>
          <p class="text-light-2 text-body-1 mb-8 max-w-2xl mx-auto">
            VirtualX transforms how people connect through immersive VR
            experiences - from livestreamed festivals to custom VR events for
            gaming, business, and social gatherings.
          </p>

          <div class="d-flex justify-center gap-4 flex-wrap">
            <v-btn
              color="blue-lighten-1"
              size="large"
              class="text-none text-white px-6 hover:scale-105"
              elevation="0"
              rounded="pill"
              @click="onClickVisitVirtualX"
            >
              <v-icon start>mdi-rocket-launch</v-icon>
              <span class="font-semibold">Investor Information</span>
            </v-btn>

            <v-btn
              variant="outlined"
              color="purple"
              size="large"
              class="text-none px-6 hover:scale-105"
              elevation="0"
              rounded="pill"
              @click="onClickUpcomingEvents"
            >
              <v-icon start>mdi-calendar-star</v-icon>
              Upcoming Virtual Events
            </v-btn>
          </div>
        </v-col>
      </v-row>
    </section>

    <!-- Key Metrics Section -->
    <section class="py-6">
      <v-row>
        <v-col cols="12">
          <v-card class="bg-dark-4 rounded-xl overflow-hidden" elevation="10">
            <div class="card-header-with-bg">
              <v-img
                src="/assets/images/vr-event.jpg"
                :height="xs ? 250 : 200"
                cover
              >
                <div class="overlay overlay-general">
                  <v-card-item>
                    <v-row>
                      <v-col cols="12" md="8">
                        <v-card-title
                          class="text-h4 font-weight-bold text-white"
                          >VirtualX at a Glance</v-card-title
                        >
                        <p class="text-grey-lighten-2 mt-2 text-body-1">
                          The future of virtual events through immersive VR
                        </p>
                      </v-col>
                      <v-col
                        cols="12"
                        md="4"
                        class="d-flex align-center justify-end"
                      >
                        <div class="text-right">
                          <div class="d-flex flex-column align-end">
                            <span class="text-h6 text-white"
                              >Development Progress</span
                            >
                            <div class="w-full mt-2">
                              <v-progress-linear
                                model-value="60"
                                color="purple"
                                height="10"
                                rounded
                              ></v-progress-linear>
                            </div>
                            <span class="text-h6 text-purple mt-1">60%</span>
                          </div>
                        </div>
                      </v-col>
                    </v-row>
                  </v-card-item>
                </div>
              </v-img>
            </div>

            <v-card-text class="pa-6">
              <v-row>
                <v-col cols="12" md="4" class="text-center">
                  <h3 class="text-h5 font-weight-bold text-purple mb-2">
                    €100,000
                  </h3>
                  <p class="text-light-2">Pre-seed investment round</p>
                </v-col>
                <v-col cols="12" md="4" class="text-center">
                  <h3 class="text-h5 font-weight-bold text-purple mb-2">
                    60/40
                  </h3>
                  <p class="text-light-2">Ownership split (VirtualX/PartyX)</p>
                </v-col>
                <v-col cols="12" md="4" class="text-center">
                  <h3 class="text-h5 font-weight-bold text-purple mb-2">
                    €5B+
                  </h3>
                  <p class="text-light-2">Global virtual events market</p>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </section>

    <!-- Platform Showcase -->
    <section class="py-6">
      <h2 class="text-h4 font-weight-bold mb-6 text-light-1">
        Experience Events Like Never Before
      </h2>
      <v-row>
        <v-col cols="12" md="6">
          <v-card class="bg-dark-4 rounded-xl h-100" elevation="10">
            <v-card-text class="pa-6">
              <h3 class="text-h5 font-weight-bold text-light-1 mb-4">
                <v-icon color="purple" class="mr-2">mdi-party-popper</v-icon>
                Live Festival Streams
              </h3>
              <p class="text-light-2 mb-4">
                Experience the energy of major festivals in real-time through
                our immersive livestream platform. Feel the music, see the
                lights, and connect with attendees from anywhere in the world.
              </p>
              <p class="text-light-2">
                Our technology provides unprecedented immersion, creating a
                sense of presence that traditional livestreams can't match.
                Interact with other virtual attendees and enjoy premium viewing
                angles.
              </p>
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="12" md="6">
          <v-card class="bg-dark-4 rounded-xl h-100" elevation="10">
            <v-card-text class="pa-6">
              <h3 class="text-h5 font-weight-bold text-light-1 mb-4">
                <v-icon color="purple" class="mr-2">mdi-virtual-reality</v-icon>
                Custom VR Events
              </h3>
              <p class="text-light-2 mb-4">
                Create and host your own virtual reality events for gaming
                tournaments, business meetings, social gatherings, and more. Our
                platform provides the tools to design customized environments
                tailored to your needs.
              </p>
              <p class="text-light-2">
                Build communities around shared interests and connect in
                meaningful ways, regardless of physical location or limitations.
              </p>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </section>

    <!-- Strategic Partnership -->
    <section class="py-6">
      <h2 class="text-h4 font-weight-bold mb-6 text-light-1">
        Strategic Partnership with PartyX
      </h2>
      <v-card class="bg-dark-4 rounded-xl" elevation="10">
        <v-card-text class="pa-6">
          <v-row align="center">
            <v-col cols="12" md="5">
              <div class="d-flex justify-center">
                <v-img
                  src="/assets/images/techno.jpg"
                  max-width="350"
                  class="rounded-xl"
                ></v-img>
              </div>
            </v-col>
            <v-col cols="12" md="7">
              <h3 class="text-h5 font-weight-bold text-light-1 mb-4">
                Leveraging Strengths Together
              </h3>
              <p class="text-light-2 mb-4">
                VirtualX has formed a strategic partnership with PartyX, the
                leading platform for authentic event experiences. This
                collaboration creates a powerful ecosystem that benefits both
                platforms:
              </p>

              <v-row>
                <v-col cols="12" md="6">
                  <div class="d-flex align-center mb-4">
                    <v-icon color="purple" class="mr-3"
                      >mdi-ticket-confirmation</v-icon
                    >
                    <div>
                      <p class="text-light-1 font-weight-bold mb-1">
                        Ticketing Integration
                      </p>
                      <p class="text-light-2 text-body-2">
                        All VirtualX events sold through PartyX's established
                        platform
                      </p>
                    </div>
                  </div>
                </v-col>

                <v-col cols="12" md="6">
                  <div class="d-flex align-center mb-4">
                    <v-icon color="purple" class="mr-3"
                      >mdi-account-group</v-icon
                    >
                    <div>
                      <p class="text-light-1 font-weight-bold mb-1">
                        User Base Growth
                      </p>
                      <p class="text-light-2 text-body-2">
                        PartyX expands audience while VirtualX gains immediate
                        users
                      </p>
                    </div>
                  </div>
                </v-col>

                <v-col cols="12" md="6">
                  <div class="d-flex align-center mb-4">
                    <v-icon color="purple" class="mr-3"
                      >mdi-currency-eur</v-icon
                    >
                    <div>
                      <p class="text-light-1 font-weight-bold mb-1">
                        Payment Processing
                      </p>
                      <p class="text-light-2 text-body-2">
                        Leveraging PartyX's secure payment infrastructure
                      </p>
                    </div>
                  </div>
                </v-col>

                <v-col cols="12" md="6">
                  <div class="d-flex align-center mb-4">
                    <v-icon color="purple" class="mr-3">mdi-handshake</v-icon>
                    <div>
                      <p class="text-light-1 font-weight-bold mb-1">
                        Event Organizer Network
                      </p>
                      <p class="text-light-2 text-body-2">
                        Immediate access to PartyX's festival and event partners
                      </p>
                    </div>
                  </div>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </section>

    <!-- Market Opportunity Section -->
    <section class="py-6">
      <h2 class="text-h4 font-weight-bold mb-6 text-light-1">
        Market Opportunity
      </h2>
      <v-row>
        <v-col cols="12" md="6">
          <v-card class="bg-dark-4 rounded-xl h-100" elevation="10">
            <v-card-text class="pa-6">
              <h3 class="text-h5 font-weight-bold text-light-1 mb-4">
                The Problem
              </h3>
              <p class="text-light-2 mb-4">
                Millions of potential attendees miss out on premium events due
                to:
              </p>
              <ul class="text-light-2 mb-6 custom-list">
                <li class="mb-2">
                  Geographic limitations (travel costs, visas)
                </li>
                <li class="mb-2">Venue capacity constraints</li>
                <li class="mb-2">
                  Personal limitations (disabilities, health concerns)
                </li>
                <li class="mb-2">
                  Financial constraints (tickets, accommodation)
                </li>
              </ul>
              <p class="text-light-2">
                Meanwhile, event organizers leave money on the table with
                limited reach and physical capacity restrictions.
              </p>
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="12" md="6">
          <v-card class="bg-dark-4 rounded-xl h-100" elevation="10">
            <v-card-text class="pa-6">
              <h3 class="text-h5 font-weight-bold text-light-1 mb-4">
                Our Solution
              </h3>
              <p class="text-light-2 mb-4">
                VirtualX bridges this gap by creating truly immersive virtual
                attendance options:
              </p>
              <ul class="text-light-2 mb-6 custom-list">
                <li class="mb-2">Livestreaming with social VR integration</li>
                <li class="mb-2">Unlimited virtual capacity for any event</li>
                <li class="mb-2">
                  Accessible pricing models for virtual tickets
                </li>
                <li class="mb-2">
                  Additional revenue streams for event organizers
                </li>
                <li class="mb-2">
                  Custom VR environments for unique experiences
                </li>
              </ul>
              <p class="text-light-2">
                Our platform transforms event limitations into global
                opportunities.
              </p>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </section>

    <!-- Roadmap & Fund Usage -->
    <section class="py-6">
      <v-row>
        <v-col cols="12" md="7">
          <h2 class="text-h4 font-weight-bold mb-6 text-light-1">
            12-Month Roadmap
          </h2>
          <v-card class="bg-dark-4 rounded-xl" elevation="10">
            <v-card-text class="pa-6">
              <v-timeline align="start" class="py-4">
                <v-timeline-item
                  v-for="(milestone, i) in milestones"
                  :key="i"
                  :dot-color="'purple'"
                  size="small"
                >
                  <template v-slot:opposite>
                    <span class="text-caption text-grey-lighten-2">{{
                      milestone.timeframe
                    }}</span>
                  </template>
                  <div>
                    <h3 class="text-h6 font-weight-bold text-light-1">
                      {{ milestone.title }}
                    </h3>
                    <p class="text-light-2">{{ milestone.description }}</p>
                  </div>
                </v-timeline-item>
              </v-timeline>
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="12" md="5">
          <h2 class="text-h4 font-weight-bold mb-6 text-light-1">
            Use of Funds
          </h2>
          <v-card class="bg-dark-4 rounded-xl" elevation="10">
            <v-card-text class="pa-6">
              <p class="text-light-2 mb-6">
                <strong>Strategy:</strong> The €100,000 pre-seed investment will
                be strategically allocated to maximize development efficiency
                while leveraging our partnership with PartyX for infrastructure
                needs.
              </p>

              <v-list class="bg-transparent pa-0">
                <v-list-item
                  v-for="(item, i) in fundUsage"
                  :key="i"
                  class="px-0 py-4"
                >
                  <template v-slot:prepend>
                    <div
                      class="text-h6 font-weight-bold text-purple w-16 text-center"
                    >
                      {{ item.percentage }}%
                    </div>
                  </template>
                  <v-list-item-title class="text-light-1 text-h6">
                    {{ item.category }}
                  </v-list-item-title>

                  <!-- Use expandedIndex to determine expanded state -->
                  <div class="mt-1">
                    <div class="d-flex align-center">
                      <p class="text-light-2 mb-0" style="line-height: 1.5">
                        {{
                          expandedIndex === i
                            ? item.description
                            : item.description.length > 20
                              ? item.description.substring(0, 20) + '...'
                              : item.description
                        }}
                      </p>
                      <v-btn
                        v-if="item.description.length > 20"
                        variant="text"
                        density="compact"
                        size="small"
                        icon
                        color="purple"
                        class="ml-2"
                        @click="toggleExpand(i)"
                      >
                        <v-icon>{{
                          expandedIndex === i
                            ? 'mdi-chevron-up'
                            : 'mdi-chevron-down'
                        }}</v-icon>
                      </v-btn>
                    </div>
                  </div>
                </v-list-item>
              </v-list>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </section>

    <!-- Business Model -->
    <section class="py-6">
      <h2 class="text-h4 font-weight-bold mb-6 text-light-1">
        Revenue Streams
      </h2>
      <v-card class="bg-dark-4 rounded-xl" elevation="10">
        <v-card-text class="pa-6">
          <v-row>
            <v-col cols="12" md="3">
              <div class="d-flex flex-column items-center mb-6">
                <v-icon color="purple" size="x-large" class="mb-4"
                  >mdi-ticket-percent</v-icon
                >
                <h3
                  class="text-h6 font-weight-bold text-center text-light-1 mb-2"
                >
                  Virtual Ticket Sales
                </h3>
                <p class="text-center text-light-2">
                  Commission on livestream and virtual event attendance tickets
                </p>
              </div>
            </v-col>

            <v-col cols="12" md="3">
              <div class="d-flex flex-column items-center mb-6">
                <v-icon color="purple" size="x-large" class="mb-4"
                  >mdi-license</v-icon
                >
                <h3
                  class="text-h6 font-weight-bold text-center text-light-1 mb-2"
                >
                  Platform Licensing
                </h3>
                <p class="text-center text-light-2">
                  B2B licensing for organizations hosting custom VR events
                </p>
              </div>
            </v-col>

            <v-col cols="12" md="3">
              <div class="d-flex flex-column items-center mb-6">
                <v-icon color="purple" size="x-large" class="mb-4"
                  >mdi-shopping</v-icon
                >
                <h3
                  class="text-h6 font-weight-bold text-center text-light-1 mb-2"
                >
                  Virtual Merchandise
                </h3>
                <p class="text-center text-light-2">
                  Digital goods, avatar customizations, and exclusive content
                </p>
              </div>
            </v-col>

            <v-col cols="12" md="3">
              <div class="d-flex flex-column items-center mb-6">
                <v-icon color="purple" size="x-large" class="mb-4"
                  >mdi-chart-box</v-icon
                >
                <h3
                  class="text-h6 font-weight-bold text-center text-light-1 mb-2"
                >
                  Premium Features
                </h3>
                <p class="text-center text-light-2">
                  VIP access, backstage passes, and artist meet-and-greets
                </p>
              </div>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </section>

    <!-- Future Vision -->
    <section class="py-6">
      <h2 class="text-h4 font-weight-bold mb-6 text-light-1">
        Future Growth Vision
      </h2>
      <v-card class="bg-dark-4 rounded-xl" elevation="10">
        <v-card-text class="pa-6">
          <p class="text-light-2 mb-6">
            With successful pre-seed funding, VirtualX will establish the
            foundation for rapid growth in these key areas:
          </p>

          <v-row>
            <v-col cols="12" md="4">
              <div class="text-center mb-6">
                <v-icon color="purple" size="x-large" class="mb-3"
                  >mdi-gamepad-variant</v-icon
                >
                <h3 class="text-h5 font-weight-bold text-light-1 mb-2">
                  Gaming & eSports
                </h3>
                <p class="text-light-2">
                  Custom VR environments for tournaments, viewing parties, and
                  gaming communities
                </p>
              </div>
            </v-col>

            <v-col cols="12" md="4">
              <div class="text-center mb-6">
                <v-icon color="purple" size="x-large" class="mb-3"
                  >mdi-briefcase</v-icon
                >
                <h3 class="text-h5 font-weight-bold text-light-1 mb-2">
                  Business Applications
                </h3>
                <p class="text-light-2">
                  Immersive corporate events, conferences, and collaborative
                  workspaces
                </p>
              </div>
            </v-col>

            <v-col cols="12" md="4">
              <div class="text-center mb-6">
                <v-icon color="purple" size="x-large" class="mb-3"
                  >mdi-heart</v-icon
                >
                <h3 class="text-h5 font-weight-bold text-light-1 mb-2">
                  Social Connections
                </h3>
                <p class="text-light-2">
                  Dating events, friend meetups, and community gatherings in
                  virtual spaces
                </p>
              </div>
            </v-col>
          </v-row>

          <p class="text-light-2 mt-4">
            By Year 3, VirtualX aims to be the premier platform for virtual
            experiences across entertainment, business, and social categories,
            with integration across major VR hardware platforms.
          </p>
        </v-card-text>
      </v-card>
    </section>

    <!-- Call to Action -->
    <section class="py-8 mb-10">
      <v-card class="bg-dark-3 rounded-xl overflow-hidden" elevation="15">
        <div class="card-header-with-bg">
          <v-img
            src="/assets/images/vr-investor.jpg"
            :height="xs ? 455 : 275"
            cover
          >
            <div class="overlay overlay-general">
              <v-container
                class="d-flex flex-column justify-center align-center text-center h-100"
              >
                <h2 class="text-h3 font-weight-bold text-white mb-6">
                  Join Us in Transforming Events
                </h2>
                <p class="text-white text-body-1 mb-8 max-w-xl mx-auto">
                  We're seeking €100,000 in pre-seed funding to bring VirtualX
                  to life and revolutionize how people experience events
                  globally.
                </p>

                <div class="d-flex justify-center gap-4 flex-wrap">
                  <v-btn
                    color="purple"
                    size="large"
                    class="text-none text-white px-6 hover:scale-105"
                    elevation="0"
                    rounded="pill"
                    @click="onClickInvestorDeck"
                  >
                    <v-icon start>mdi-file-document</v-icon>
                    <span class="font-semibold">Investor Deck</span>
                  </v-btn>

                  <v-btn
                    variant="outlined"
                    color="white"
                    size="large"
                    class="text-none px-6 hover:scale-105"
                    elevation="0"
                    rounded="pill"
                    @click="onClickScheduleCall"
                  >
                    <v-icon start>mdi-calendar-clock</v-icon>
                    Schedule a Call
                  </v-btn>
                </div>
              </v-container>
            </div>
          </v-img>
        </div>
      </v-card>
    </section>
  </v-container>
</template>

<style>
/* global background color */
body {
  background-color: #1c1c1e;
}

/* target the root div (v-app) */
.v-application {
  background-color: #1c1c1e;
}

:root {
  /* Gray Scale from the provided colors */
  --color-gray-1: #8e8e93;
  --color-gray-2: #636366;
  --color-gray-3: #48484a;
  --color-gray-4: #3a3a3c;
  --color-gray-5: #2c2c2e;
  --color-gray-6: #1c1c1e;

  /* Accent colors */
  --color-blue: #0a84ff;
  --color-blue-dark: #0066cc;
  --color-blue-accent: #36a3ff;
  --color-purple: #bf5af2;
  --color-purple-dark: #9945c7;
  --color-gold: #ffd60a;
  --color-gold-dark: #e6b800;
}

/* Background Classes */
.bg-dark {
  background-color: var(--color-gray-6) !important;
}
.bg-dark-5 {
  background-color: var(--color-gray-5) !important;
}
.bg-dark-4 {
  background-color: var(--color-gray-4) !important;
}
.bg-dark-3 {
  background-color: var(--color-gray-3) !important;
}

/* Text Colors */
.text-light-1 {
  color: #ffffff !important;
}
.text-light-2 {
  color: rgba(255, 255, 255, 0.8) !important;
}
.text-dark-6 {
  color: var(--color-gray-6) !important;
}
.text-blue {
  color: var(--color-blue) !important;
}
.text-blue-accent {
  color: var(--color-blue-accent) !important;
}
.text-purple {
  color: var(--color-purple) !important;
}
.text-gold {
  color: var(--color-gold) !important;
}

/* Text Gradient */
.text-gradient {
  background: linear-gradient(135deg, var(--color-purple), var(--color-blue));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  text-fill-color: transparent;
}

/* Custom Styles */
.text-none {
  text-transform: none !important;
}

/* Card headers with background images */
.card-header-with-bg {
  position: relative;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 24px;
  backdrop-filter: blur(1px);
}

/* Optimized overlay gradients for better text visibility */
.overlay-general {
  background: linear-gradient(
    135deg,
    rgba(10, 12, 33, 0.78),
    rgba(46, 0, 76, 0.89)
  ) !important;
}

.max-w-xl {
  max-width: 36rem;
}

.max-w-2xl {
  max-width: 42rem;
}

.h-100 {
  height: 100%;
}

.w-16 {
  width: 4rem;
}

.custom-list {
  list-style: none;
  padding-left: 0;
}

.custom-list li {
  position: relative;
  padding-left: 1.5rem;
}

.custom-list li::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0.5rem;
  width: 0.5rem;
  height: 0.5rem;
  background-color: var(--color-purple);
  border-radius: 50%;
}
/* Adjust the size and position of the bullet */

.custom-list li::before {
  margin-top: 0.2rem;
  margin-left: -0.5rem;
}
</style>
