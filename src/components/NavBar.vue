<template>
  <div class="bg-blue-700 text-coolGray-400 py-6">
    <div class="container mx-auto flex justify-between items-center">
      <div class="brand flex space-x-2 text-3xl">
        <mdi:chat class="text-yellow-500 w-9 h-9 mt-1 animate-ping" />
        <h1 class="font-thin">
          Chit<span class="font-bold text-yellow-300">Chat</span>
        </h1>
      </div>
      <div class="menu">
        <div v-if="!isAuthenticated">
          <button
            class="bg-yellow-300 text-blue-500 py-2 px-4 rounded-full hover:bg-green-900 focus:outline-none focus:ring-4 focus:ring-green-500"
            @click="googlePopup"
          >
            Login
          </button>
        </div>
        <div v-else class="flex items-center space-x-8">
          <p>Welcome {{ user?.displayName }}</p>
          <button
            class="bg-indigo-800 text-white py-2 px-4 rounded-full hover:bg-indigo-300 focus:outline-none focus:ring-4 focus:ring-red-500"
            @click="signOut"
          >
            Logout
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { authentication } from "~/helpers/useFirebase";

const { isAuthenticated, user, googlePopup, signOut } = authentication();
</script>
