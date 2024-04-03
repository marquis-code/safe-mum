<template>
  <div class="bg-white py-24 sm:py-32">
    <div class="mx-auto grid max-w-7xl gap-x-8 gap-y-20 px-6 lg:px-8 xl:grid-cols-3">
      <div class="max-w-2xl">
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Meet our leadership</h2>
        <p class="mt-6 text-lg leading-8 text-gray-600">Our team is our proudest asset, embodying
          innovation, dedication, and a relentless pursuit of excellence. Together, we're not just setting standards;
          we're redefining them. Get to know the brilliant minds propelling us forward.</p>
      </div>
      <ul role="list" class="grid gap-x-8 gap-y-12 sm:grid-cols-2 sm:gap-y-16 xl:col-span-2">
        <li v-for="itm in members" :key="itm.name">
          <div class="flex items-center gap-x-6">
            <img class="h-16 w-16 rounded-full border shadow" :src="require(`@/assets/img/${itm.image}.jpeg`)" alt="">
            <div>
              <h3 class="text-base font-semibold leading-7 tracking-tight text-gray-900">{{ itm.name }}</h3>
              <p class="text-sm font-semibold leading-6 text-indigo-600">{{ itm.position }}</p>
            </div>
          </div>
        </li>

        <!-- More people... -->
      </ul>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      members: [
        {
          image: 'ceo',
          name: 'Micheal Sunmoni',
          position: 'Chief Executive Officer (CEO)'
        },
        {
          image: 'cmo',
          name: 'Jesulewami Oreweme',
          position: 'Chief Marketing Officer (CMO)'
        },
        {
          image: 'coo',
          name: 'Abdulkhaliq Abdulrasaq',
          position: 'Chief Operating Officer (COO)'
        },
        {
          image: 'cto',
          name: 'Joshua Saanumi',
          position: 'Chief Technology Officer (CTO)'
        },
        {
          image: 'ai',
          name: 'Marquis Abah',
          position: 'AI Engineer'
        }
      ]
    }
  }
}
</script>
