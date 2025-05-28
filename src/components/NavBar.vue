<template>
  <nav class="fixed top-0 left-0 w-full bg-gray-800 text-white shadow-md z-50">
    <div class="container mx-auto px-6 py-4 flex justify-end space-x-8">
      <div class="group relative">
        <span class="cursor-pointer">Support</span>
        <ul class="absolute right-0 mt-2 bg-white text-black rounded shadow-lg hidden group-hover:block">
          <li class="px-4 py-2 hover:bg-gray-200 cursor-pointer">Get Help</li>
          <li class="px-4 py-2 hover:bg-gray-200 cursor-pointer">Contact Us</li>
        </ul>
      </div>
      <div class="group relative">
        <span class="cursor-pointer">About</span>
        <ul class="absolute right-0 mt-2 bg-white text-black rounded shadow-lg hidden group-hover:block">
          <li class="px-4 py-2 hover:bg-gray-200 cursor-pointer">Us</li>
          <li class="px-4 py-2 hover:bg-gray-200 cursor-pointer">You</li>
          <li class="px-4 py-2 hover:bg-gray-200 cursor-pointer">The Mission</li>
          
        </ul>
      </div>
      <div class="group relative">
        <span class="cursor-pointer">Settings</span>
        <ul class="absolute right-0 mt-2 bg-white text-black rounded shadow-lg hidden group-hover:block">
          <li class="px-4 py-2 hover:bg-gray-200 cursor-pointer">Profile</li>
          <li class="px-4 py-2 hover:bg-gray-200 cursor-pointer">Security</li>
          <li class="px-4 py-2 hover:bg-gray-200 cursor-pointer">Developer</li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
</script>
