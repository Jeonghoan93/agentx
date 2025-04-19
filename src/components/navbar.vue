<script setup lang="ts">
const router = useRouter()

const headersElements: {
  title: string
  subItems: { title: string; route: string }[]
}[] = [
  {
    title: 'Investors',
    subItems: [{ title: 'Pitch Deck', route: '/investors' }]
  },
  {
    title: 'Products',
    subItems: [
      { title: 'AI Solutions & Integrations', route: '/products/hr' },
      { title: 'Robotics', route: '/products/robotics' }
    ]
  },
  {
    title: 'Solutions',
    subItems: [
      { title: 'For Teams', route: '/solutions/teams' },
      { title: 'For Startups', route: '/solutions/startups' }
    ]
  },
  {
    title: 'Pricing',
    subItems: [
      { title: 'Plans', route: '/pricing/plans' },
      { title: 'Enterprise', route: '/pricing/enterprise' }
    ]
  },
  {
    title: 'Login',
    subItems: [
      { title: 'Sign in', route: '/login' },
      { title: 'Register', route: '/register' }
    ]
  }
]

const onClickNavigateToLinkedin = () => {
  window.open('https://www.linkedin.com', '_blank')
}
</script>
<template>
  <header class="w-full border-b bg-gray-6 shadow h-[57px] fixed z-50">
    <v-container>
      <div class="flex items-center justify-between">
        <div class="w-36">
          <span
            class="text-[#f7f7f7] cursor-pointer font-extrabold text-[14pt]"
            @click="() => router.push('/')"
          >
            AgentX
          </span>
        </div>

        <!-- Desktop View -->
        <div class="flex flex-row gap-4 items-center">
          <template v-for="(header, index) in headersElements" :key="index">
            <v-menu>
              <template #activator="{ props }">
                <v-btn
                  v-bind="props"
                  size="small"
                  variant="text"
                  class="normal-case text-white text-xs font-semibold"
                >
                  <span class="font-semibold text-slate-200">
                    {{ header.title }}
                  </span>
                </v-btn>
              </template>

              <v-card class="px-3">
                <v-list>
                  <v-list-item
                    v-for="(item, idx) in header.subItems"
                    :key="idx"
                    @click="router.push(item.route)"
                  >
                    <v-list-item-title>
                      <span class="text-gray-6 text-xs font-semibold">
                        {{ item.title }}
                      </span>
                    </v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-card>
            </v-menu>
          </template>

          <v-btn class="ml-3" @click="onClickNavigateToLinkedin" size="small">
            <span class="font-semibold"> Sign up now </span>
          </v-btn>
        </div>

        <!-- Mobile View -->
        <!-- TODO: Create Mobile View -->
      </div>
    </v-container>
  </header>
</template>
