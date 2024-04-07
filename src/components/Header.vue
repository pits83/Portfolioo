<script setup>
// Social Links - Update this links to your link
const FacebookLink = 'https://www.facebook.com/profile.php?id=61552191183300';

// JavaScript to toggle the mobile navigation menu
document.addEventListener("DOMContentLoaded", function() {
    const mobileMenuButton = document.getElementById("mobileMenuButton");
    const navbarSticky = document.getElementById("navbarSticky");

    mobileMenuButton.addEventListener("click", function() {
        const expanded = navbarSticky.getAttribute("aria-expanded") === "true";
        navbarSticky.setAttribute("aria-expanded", !expanded);
        navbarSticky.classList.toggle("hidden");
    });
});

</script>

<template>
    <header class="bg-white mt-5">
        <div class="mx-auto max-w-screen-xl px-12 py-2">
            <div class="flex flex-row items-center justify-between">

                <nav class="bg-white dark:bg-white-900 fixed w-full z-20 top-0 left-0 border-b border-gray-200 dark:border-gray-600">
                    <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto">
                        <router-link to="/" class="flex flex-col items-center">
                            <img src="../assets/slogo.jpg" alt="Your Logo" class="h-12 w-12 rounded-full">
                        </router-link>
                        <div class="flex md:order-2">
                            <ul class="flex flex-row items-center gap-4">
                                <a :href="FacebookLink" target="_blank"
                                    class="bg-gradient-to-br from-gray-100 via-gray-200 to-gray-100 hover:from-gray-200 hover:via-gray-300 hover:to-gray-200 p-3 rounded-full transition-all duration-300 transform hover:-rotate-3">
                                    <svg class="w-5 h-5 text-gray-600" aria-hidden="true"
                                        xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 8 19">
                                        <path fill-rule="evenodd"
                                            d="M6.135 3H8V0H6.135a4.147 4.147 0 0 0-4.142 4.142V6H0v3h2v9.938h3V9h2.021l.592-3H5V3.591A.6.6 0 0 1 5.592 3h.543Z"
                                            clip-rule="evenodd" />
                                    </svg>
                                </a>
                            </ul>
                        </div>
                        <div class="md:hidden">
                            <button id="mobileMenuButton" type="button" class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="navbar-sticky" aria-expanded="false">
                                <span class="sr-only">Open main menu</span>
                                <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
                                </svg>
                            </button>
                        </div>
                        
                        <div id="navbarSticky" class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1">
                            
                            <ul class="flex flex-col gap-2 mt-2 mb-4 lg:mb-0 lg:mt-0 lg:flex-row lg:items-center lg:gap-6">
                                <li
                                    :class="$route.name === 'home' ? 'text-blue-700 font-medium text-lg' : 'text-gray-700 hover:text-blue-700 font-normal text-lg'">
                                    <router-link to="/">Home</router-link>
                                </li>
                                <li
                                    :class="$route.name === 'about' ? 'text-blue-700 font-medium text-lg' : 'text-gray-700 hover:text-blue-700 font-normal text-lg'">
                                    <router-link to="/about">About</router-link>
                                </li>
                                <li
                                    :class="$route.name === 'projects' ? 'text-blue-700 font-medium text-lg' : 'text-gray-700 hover:text-blue-700 font-normal text-lg'">
                                    <router-link to="/projects">Projects</router-link>
                                </li>
                                <li
                                    :class="$route.name === 'diary' ? 'text-blue-700 font-medium text-lg' : 'text-gray-700 hover:text-blue-700 font-normal text-lg'">
                                    <router-link to="/notepad">NotePad</router-link>
                                </li>
                                
                                <li
                                    :class="$route.name === 'contact' ? 'text-blue-700 font-medium text-lg' : 'text-gray-700 hover:text-blue-700 font-normal text-lg'">
                                    <router-link to="/contact">Contact</router-link>
                                </li>
                                
                            </ul>
                        </div>
                    </div>
                </nav>         
            </div>
        </div>
    </header>
</template>