<script>
  import { slide } from "svelte/transition";
  let mobileMenuOpen = $state(false);

  const toggleMenu = () => {
    mobileMenuOpen = !mobileMenuOpen;
  };
</script>

<nav
  class="fixed flex w-full z-20 justify-between items-center px-9 py-6 text-white bg-amber-950"
>
  <h1 class="text-2xl font-bold">Caffeine</h1>

  <!-- Menu items for larger screens -->
  <ul class="hidden md:flex gap-8 text-lg">
    <li><a href="#" aria-label="Home">Home</a></li>
    <li><a href="#" aria-label="Menu">Menu</a></li>
    <li><a href="#" aria-label="About Us">About Us</a></li>
    <li><a href="#" aria-label="Facilities">Facilities</a></li>
  </ul>

  <!-- Sign In button for larger screens -->
  <button class="hidden md:block border px-4 py-2 rounded" aria-label="Sign In"
    >Sign In</button
  >

  <!-- Hamburger Menu for mobile -->
  <button
    class="md:hidden text-white focus:outline-none"
    aria-label="Open menu"
    onclick={toggleMenu}
  >
    <i class="fas fa-bars text-3xl cursor-pointer" aria-hidden="true"></i>
  </button>
</nav>

<!-- Mobile Menu -->
{#if mobileMenuOpen}
  <div
    transition:slide
    class="md:hidden fixed top-0 left-0 w-full h-full bg-black bg-opacity-50 z-100"
  >
    <div class="flex justify-end px-9 py-6">
      <button onclick={toggleMenu} aria-label="Close menu" class="text-white">
        <i class="fas fa-times text-4xl cursor-pointer" aria-hidden="true"></i>
      </button>
    </div>
    <ul class="flex flex-col gap-3 px-10 text-white text-xl">
      <li class="text-3xl border-b-1 border-b-white py-5">
        <a href="#" class="py-3 cursor-pointer" aria-label="Home">Home</a>
      </li>
      <li class="text-3xl border-b-1 border-b-white py-5">
        <a href="#" class="py-3 cursor-pointer" aria-label="Menu">Menu</a>
      </li>
      <li class="text-3xl border-b-1 border-b-white py-5">
        <a href="#" class="py-3 cursor-pointer" aria-label="About Us"
          >About Us</a
        >
      </li>
      <li class="text-3xl border-b-1 border-b-white py-5">
        <a href="#" class="py-3 cursor-pointer" aria-label="Facilities"
          >Facilities</a
        >
      </li>
      <li class="text-3xl border-b-1 border-b-white py-5">
        <a href="#" class="py-3 cursor-pointer" aria-label="Sign In">Sign In</a>
      </li>
    </ul>
  </div>
{/if}
