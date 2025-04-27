<script>
  import Navbar from "$lib/components/Navbar.svelte";

  const coffees = [
    { name: "Cappuccino", img: "/cappuccino.jpg" },
    { name: "Americano", img: "/americano.jpg" },
    { name: "Espresso", img: "/espresso.jpg" },
  ];

  const testimonials = [
    {
      name: "Shalima Hayden",
      review:
        "I have tested Caffeine coffee many times. Really amazing to me. The combination was very good.",
      stars: 5,
      img: "/user.jpg",
    },
  ];
</script>

<!-- Navbar -->
<Navbar />

<!-- hero section -->
<section
  class="flex lg:flex-row flex-col bg-[#1c1b18] text-white min-h-screen lg:px-20 px-3 py-20"
>
  <!-- Hero Section -->
  <div
    class="flex md:flex-row flex-col items-center lg:p-10 p-3 gap-8 lg:w-1/2"
  >
    <div class="flex flex-col gap-10 lg:p-10 p-3">
      <h2 class="text-5xl md:text-6xl font-bold text-balance">
        Discover The Art Of Perfect Coffee
      </h2>
      <p class="text-gray-300 text-balance">
        Experience the rich and bold flavors of our exquisite coffee blends,
        crafted to awaken your senses and start your day right.
      </p>
      <div class="flex gap-4">
        <button
          class="bg-white cursor-pointer active:scale-95 transition-all text-black px-6 py-3 rounded hover:bg-gray-200"
          >Order Now</button
        >
        <button
          class="border px-6 py-3 cursor-pointer active:scale-95 transition-all rounded hover:bg-white hover:text-black"
          >Explore More</button
        >
      </div>
      <!-- badges -->
      <div class="flex gap-8 pt-6">
        <div>
          <span class="text-2xl font-bold">50+</span>
          <p>Item of Coffee</p>
        </div>
        <div>
          <span class="text-2xl font-bold">20+</span>
          <p>Order Running</p>
        </div>
        <div>
          <span class="text-2xl font-bold">2k+</span>
          <p>Happy Customer</p>
        </div>
      </div>
      <!-- badges end -->
    </div>
  </div>
  <!-- coffee image -->
  <div class="lg:w-1/2">
    <img src="coffee.png" alt="Coffee Splash" class="w-full rounded-lg" />
  </div>
</section>

<!-- Coffees Section -->
<section class="bg-[#f3e4d4] py-20">
  <div class="max-w-6xl mx-auto px-6">
    <h3 class="text-3xl font-bold text-center mb-12">Our Coffees</h3>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-10">
      {#each coffees as coffee}
        <div class="bg-white shadow-lg p-6 rounded-lg text-center">
          <img
            src={coffee.img}
            alt={coffee.name}
            class="w-full h-40 object-cover mb-6 rounded"
          />
          <h4 class="text-xl font-bold mb-4">{coffee.name}</h4>
          <button
            class="bg-black text-white px-4 py-2 rounded hover:bg-gray-800"
            >Order Now</button
          >
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Testimonial Section -->
<section class="bg-[#f5f5f5] py-20">
  <div class="max-w-4xl mx-auto text-center px-6">
    <h3 class="text-3xl font-bold mb-10">What Our Customer Says</h3>
    {#each testimonials as t}
      <div class="bg-white p-8 rounded-lg shadow">
        <img
          src={t.img}
          alt={t.name}
          class="w-16 h-16 mx-auto rounded-full mb-4"
        />
        <p class="text-gray-600 mb-4">"{t.review}"</p>
        <div class="text-yellow-500 mb-2">
          {"★".repeat(t.stars)}
        </div>
        <p class="font-bold">{t.name}</p>
      </div>
    {/each}
  </div>
</section>

<!-- Newsletter Section -->
<section class="bg-[#1c1b18] text-white py-16">
  <div class="max-w-4xl mx-auto text-center px-6">
    <h3 class="text-3xl font-bold mb-6">Stay Up To Date</h3>
    <p class="mb-8 text-gray-400">
      Be the first to know about new collections, special events, and what's
      going on at Caffeine.
    </p>
    <div class="flex flex-col md:flex-row items-center justify-center gap-4">
      <input
        type="email"
        placeholder="Enter your email"
        class="px-6 py-3 w-full w-1/2 rounded text-black"
      />
      <button class="bg-white text-black px-6 py-3 rounded hover:bg-gray-200"
        >Subscribe</button
      >
    </div>
  </div>
</section>

<!-- Footer -->
<footer class="bg-black text-gray-400 text-center p-6">
  <p>Contact Us: Caffeine@Gmail.Com | (321) 562-57420</p>
</footer>
