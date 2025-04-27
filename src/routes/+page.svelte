<script>
  // AOS
  import { onMount } from "svelte";
  import "aos/dist/aos.css"; // Import AOS styles

  // Initialize AOS when the component is mounted
  onMount(() => {
    import("aos").then((AOS) => {
      AOS.init({
        duration: 500, // Animation duration
        easing: "ease-out", // Easing function
      });
    });
  });

  import Navbar from "$lib/components/Navbar.svelte";

  const coffees = [
    {
      name: "Cappuccino",
      img: "https://plus.unsplash.com/premium_photo-1674327105074-46dd8319164b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    },
    {
      name: "Americano",
      img: "https://images.unsplash.com/photo-1461023058943-07fcbe16d735?q=80&w=2069&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    },
    {
      name: "Espresso",
      img: "https://images.unsplash.com/photo-1541167760496-1628856ab772?q=80&w=1937&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    },
  ];

  const testimonials = [
    {
      name: "Shalima Hayden",
      review:
        "I have tested Caffeine coffee many times. Really amazing to me. The combination was very good.",
      stars: 5,
      img: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    },
    {
      name: "John Doe",
      review:
        "Best coffee in town! Friendly staff, cozy atmosphere, and consistently delicious brews. A must-visit for every coffee lover!",
      stars: 5,
      img: "https://plus.unsplash.com/premium_photo-1689977807477-a579eda91fa2?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    },
  ];
</script>

<!-- Navbar -->
<Navbar />

<!-- hero section -->
<section
  class="flex lg:flex-row flex-col text-white min-h-screen lg:px-20 px-3 py-24"
>
  <!-- bg -->
  <div
    class="flex justify-center items-center min-h-screen fixed top-0 right-0 -z-10 bg-[#1c1b18] w-full"
  >
    <h1 class="text-gray-500 opacity-20 lg:text-[500px] text-[200px] font-bold">
      Caffeine
    </h1>
  </div>
  <!-- Hero Section -->
  <div
    class="flex md:flex-row flex-col items-center lg:p-10 p-3 gap-8 lg:w-1/2"
  >
    <div class="flex flex-col gap-10 lg:p-10 p-3">
      <h2 class="text-5xl md:text-7xl font-bold text-balance">
        Discover The Art Of Perfect Coffee
      </h2>
      <p class="text-gray-300 text-balance md:text-3xl">
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
  <div class="mx-auto px-6">
    <h3 class="text-5xl font-bold text-center mb-12">Our Coffees</h3>
    <div class="flex flex-wrap gap-10 justify-center items-center">
      {#each coffees as coffee, i}
        <div
          data-aos="fade-up"
          data-aos-delay="{i}00"
          class="bg-white shadow-lg p-3 rounded-xl w-120"
        >
          <img
            src={coffee.img}
            alt={coffee.name}
            class="w-full h-70 object-cover mb-6 rounded"
          />
          <div>
            <h4 class="text-3xl font-bold mb-4">{coffee.name}</h4>
          </div>
          <div class="flex justify-end">
            <button
              class="bg-black text-white text-3xl px-4 py-2 rounded hover:bg-gray-800 active:scale-95 transition-all cursor-pointer"
              >Order Now</button
            >
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Testimonial Section -->
<section class="bg-white py-20 flex flex-col justify-center items-center">
  <div class="text-center px-6">
    <h3 class="lg:text-7xl text-3xl font-extrabold mb-20">
      What Our Customers Say
    </h3>
    <div class="flex flex-wrap justify-center items-center gap-5">
      {#each testimonials as t}
        <div
          data-aos="fade-up"
          class="bg-amber-900 flex flex-col justify-center items-center gap-5 text-white p-8 rounded-xl shadow md:w-180 h-96"
        >
          <img
            src={t.img}
            alt={t.name}
            class="rounded-full mx-auto w-28 aspect-square object-cover"
          />
          <p class="text-xl">"{t.review}"</p>
          <div class="text-yellow-500">
            {"★".repeat(t.stars)}
          </div>
          <p class="font-bold text-3xl">{t.name}</p>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Newsletter Section -->
<section class="relative text-white py-24">
  <!-- Overlay with reduced opacity -->
  <div class="absolute inset-0 bg-black opacity-20"></div>
  <!-- Change opacity here -->

  <!-- Background image -->
  <div
    class="absolute inset-0 bg-cover bg-center"
    style="background-image: url('https://plus.unsplash.com/premium_photo-1675237625862-d982e7f44696?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');"
  ></div>

  <!-- Content inside the section -->
  <div class="relative z-10 max-w-4xl mx-auto text-center px-6">
    <h3 class="lg:text-8xl text-4xl font-bold mb-8">Stay Up To Date</h3>
    <!-- Increased text size -->
    <p class="mb-8 text-2xl">
      <!-- Increased paragraph text size -->
      Be the first to know about new collections, events, and what's going
      on at Caffeine.
    </p>
    <div class="flex items-center justify-center">
      <input
        type="email"
        placeholder="Enter your email"
        class="px-6 py-3 w-full rounded border-1 border-white rounded-tr-none rounded-br-none placeholder-white"
      />
      <button
        class="bg-white text-black px-6 py-3 rounded hover:bg-gray-200 rounded-bl-none rounded-tl-none border-1 border-white cursor-pointer"
        >Subscribe</button
      >
    </div>
  </div>
</section>

<!-- Footer -->
<footer class="bg-black text-gray-400 text-center p-6">
  <p>Contact Us: caffeine@Gmail.Com | (321) 562-57420</p>
</footer>
