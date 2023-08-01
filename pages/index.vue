<script lang="ts" setup>
import '~~/composables/useWpApi'

  // Call API use fetch
  
  const { data: posts, refresh, error } = await useWpApi().getPosts()

  // console.log(posts)
  
  useHead({
  title: "Home",
  meta: [
    {
      name: "description",
      content: "Home",
    },
    {
      name: "keywords",
      content: "Home, Nuxt 3, Learning Nuxt 3",
    },
  ],
})
</script>

<template>
  <main>
    <section id="hero" class="text-gray-600 body-font"
      >
      <div
        class="container mx-auto px-4 xl:px-0 flex flex-col sm:flex-row items-center justify-between gap-6 sm:gap-20"
      >
        <div class="w-full sm:w-6/12">
          <h1
            class="text-4xl sm:text-6xl font-bold xl:leading-[4rem] text-skin-base"
          >
            Nuxt 3 Tailwind : ค้นหาผู้ผ่านการฝึกอาชีพในพื้นที่ใกล้เคียง
          </h1>
          <p class="text-xl mt-4 mb-14 text-skin-muted">
            Nuxt 3 + Tailwind CSS for Starter kit
          </p>
          <!--part of searching box-->
          <div></div>

          <div class="space-x-4">
            <button
              class="text-2xl text-white px-4 py-3 bg-teal-700 rounded-lg"
            >
              Get Start ค้นหา
            </button>
          </div>
        </div>
        <div class="w-full sm:w-6/12 flex justify-end p-2 sm:p-0">
          <img
            loading="lazy"
            src="~/assets/images/sunf3.png"
            class="w-auto rounded-lg"
          />
        </div>
      </div>
    </section>
    <!-- Blog Section Starts -->
    <section class="container mx-auto">
      <div class="container py-10">
        <div class="grid sm:grid-cols-3 gap-10">
          <BlogGrid
            v-for="post in posts"
            :key="post.id"
            :title="post.title.rendered"
            :image="post._embedded['wp:featuredmedia'][0]?.source_url"
            :excerpt="post.excerpt.rendered"
            :slug="post.slug"
          ></BlogGrid>
    
          <BlogGrid
            title="The Dark Truth About Baby Cereal"
            image="https://www.itgenius.co.th/sandbox_api/flutter_news_api/wp-content/uploads/2021/06/little-girl-home-with-cart-vegetables_231056-89.jpg"
            excerpt="Baby cereal was first introduced in the 1930s, which was when a monumental shift occurred away from real foods towards processed convenience foods. Previously known as pablum, mothers were advised to mix it into a bottle with breast milk for babies as young as six weeks old"
            slug="https://www.itgenius.co.th/sandbox_api/flutter_news_api/the-dark-truth-about-baby-cereal/"
          ></BlogGrid>

          <BlogGrid
            title="Best Baby Games: Birth to 18 Months"
            image="https://www.itgenius.co.th/sandbox_api/flutter_news_api/wp-content/uploads/2021/06/little-boy-plays-with-colorful-pyramid-white-background-with-space-text_208700-1860.jpeg"
            excerpt="Never Too Young for Fun</h2>\n\n\n\n<p>Something about the stuffed animal we dubbed “crinkle puppy” for its crinkly sound when squeezed left my daughter Emma, 3 months at the time, smiling each time I placed it in front of her. Maybe it was the contrasting colors that held Emma’s attention. It could have been the way I often “spoke” for the puppy, giving Emma an idea of what a real puppy would sound"
            slug="https://www.itgenius.co.th/sandbox_api/flutter_news_api/best-baby-games-birth-to-18-months/"
          ></BlogGrid>

          <BlogGrid
            title="Easy Tips for Grooming Your Newborn"
            image="https://www.itgenius.co.th/sandbox_api/flutter_news_api/wp-content/uploads/2021/06/woman-brushing-young-girl-s-hair-while-sitting-near-window-woman-combing-her-3-year-old-daughter-s-hair_73762-537.jpg"
            excerpt="Grooming a newborn can be a nerve-wracking experience, especially for first-time parents From caring for the umbilical cord to trimming tiny nails, parents have a lot to learn when it comes to keeping their little ones “baby fresh. Liz Drake, a clinical nurse specialist in the neonatal intensive care unit at CHOC Children"
            slug="https://www.itgenius.co.th/sandbox_api/flutter_news_api/easy-tips-for-grooming-your-newborn/"
          ></BlogGrid>
        </div>
      </div>
    </section>
    <!-- Blog Section Ends  -->

    <!--section 2-->
    <section class="text-gray-600 body-font">
      <div class="container px-5 py-24 mx-auto flex flex-wrap">
        <div
          class="bg-green-50 lg:w-1/2 w-full mb-10 lg:mb-0 rounded-lg overflow-hidden"
        >
          <img
            alt="feature"
            class="object-center w-full h-75"
            src="~/assets/images/sunf.jpg"
          />
        </div>
        <div
          class="flex flex-col flex-wrap lg:py-6 -mb-10 lg:w-1/2 lg:pl-12 lg:text-left text-center"
        >
          <div class="flex flex-col mb-10 lg:items-start items-center">
            <div
              class="w-12 h-12 inline-flex items-center justify-center rounded-full bg-indigo-100 text-indigo-500 mb-5"
            >
              <svg
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-6 h-6"
                viewBox="0 0 24 24"
              >
                <path d="M22 12h-4l-3 9L9 3l-3 9H2"></path>
              </svg>
            </div>
            <div class="flex-grow">
              <h2 class="text-gray-900 text-lg title-font font-medium mb-3">
                Shooting Stars
              </h2>
              <p class="leading-relaxed text-base">
                Blue bottle crucifix vinyl post-ironic four dollar toast vegan
                taxidermy. Gastropub indxgo juice poutine.
              </p>
              <a class="mt-3 text-indigo-500 inline-flex items-center"
                >Learn More
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-4 h-4 ml-2"
                  viewBox="0 0 24 24"
                >
                  <path d="M5 12h14M12 5l7 7-7 7"></path>
                </svg>
              </a>
            </div>
          </div>
          <div class="flex flex-col mb-10 lg:items-start items-center">
            <div
              class="w-12 h-12 inline-flex items-center justify-center rounded-full bg-indigo-100 text-indigo-500 mb-5"
            >
              <svg
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-6 h-6"
                viewBox="0 0 24 24"
              >
                <circle cx="6" cy="6" r="3"></circle>
                <circle cx="6" cy="18" r="3"></circle>
                <path
                  d="M20 4L8.12 15.88M14.47 14.48L20 20M8.12 8.12L12 12"
                ></path>
              </svg>
            </div>
            <div class="flex-grow">
              <h2 class="text-gray-900 text-lg title-font font-medium mb-3">
                The Catalyzer
              </h2>
              <p class="leading-relaxed text-base">
                Blue bottle crucifix vinyl post-ironic four dollar toast vegan
                taxidermy. Gastropub indxgo juice poutine.
              </p>
              <a class="mt-3 text-indigo-500 inline-flex items-center"
                >Learn More
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-4 h-4 ml-2"
                  viewBox="0 0 24 24"
                >
                  <path d="M5 12h14M12 5l7 7-7 7"></path>
                </svg>
              </a>
            </div>
          </div>
          <div class="flex flex-col mb-10 lg:items-start items-center">
            <div
              class="w-12 h-12 inline-flex items-center justify-center rounded-full bg-indigo-100 text-indigo-500 mb-5"
            >
              <svg
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-6 h-6"
                viewBox="0 0 24 24"
              >
                <path d="M20 21v-2a4 4 0 00-4-4H8a4 4 0 00-4 4v2"></path>
                <circle cx="12" cy="7" r="4"></circle>
              </svg>
            </div>
            <div class="flex-grow">
              <h2 class="text-gray-900 text-lg title-font font-medium mb-3">
                Neptune
              </h2>
              <p class="leading-relaxed text-base">
                Blue bottle crucifix vinyl post-ironic four dollar toast vegan
                taxidermy. Gastropub indxgo juice poutine.
              </p>
              <a class="mt-3 text-indigo-500 inline-flex items-center"
                >Learn More
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-4 h-4 ml-2"
                  viewBox="0 0 24 24"
                >
                  <path d="M5 12h14M12 5l7 7-7 7"></path>
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
animation: bounce 1s infinite;

@keyframes bounce {
  0%,
  100% {
    transform: translateY(-5%);
    animation-timing-function: cubic-bezier(0.8, 0, 1, 1);
  }
  50% {
    transform: translateY(0);
    animation-timing-function: cubic-bezier(0, 0, 0.2, 1);
  }
}
</style>
