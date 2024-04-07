
<template>
    <section class="flex flex-col justify-between gap-6 sm:gap-10 md:gap-16 lg:flex-row py-16 ">
        
        <!-- content - start -->
    <div class="flex flex-col-reverse xl:flex-row justify-between xl:w-full">
        <div class="xl:w-5/12">
            <div class="sm:text-center lg:py-14 lg:text-left xl:py-28">
                <h2 class="mb-4 text-4xl font-bold md:text-6xl">Hi, I am Sherly Mae Escolar </h2>
                <h4 class="mb-7 text-5xl text-gray-900 sm:text-2xl">UI & Graphic Designer </h4>
                <div class="flex flex-col gap-2.5 sm:flex-row sm:justify-center lg:justify-start">
                <router-link to="/contact"
                    class="inline-block rounded-lg bg-gray-200 px-3 py-2 text-center text-sm font-semibold text-yellow-700 outline-none 
                    ring-indigo-300 transition duration-100 hover:transform hover:scale-105 hover:bg-gray-300 hover:shadow-xl focus:shadow-md active:shadow-md md:text-base">
                    CONTACT ME 
                </router-link>
                </div>

            </div>  
        </div>
        <div class="relative h-48 overflow-hidden rounded-lg transform hover:scale-105 transition-transform duration-300 lg:h-auto xl:w-5/12">
            <img src="../assets/she.jpg" class="h-80 sm:h-full w-50 object-cover object-center" />
        </div>
    </div>

    </section>
</template>
