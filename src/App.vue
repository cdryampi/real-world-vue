<template>
  <div class="bg-white">
    <!-- Header -->
    <header class="absolute inset-x-0 top-0 z-50">
      <nav class="flex items-center justify-between p-6 lg:px-8" aria-label="Global">
        <div class="flex lg:flex-1">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only">Fundamentos de JavaScript</span>
            <img
              class="h-8 w-auto"
              src="https://tailwindui.com/plus/img/logos/mark.svg?color=indigo&shade=600"
              alt="Logo"
            />
          </a>
        </div>
        <div class="flex lg:hidden">
          <button
            type="button"
            class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
          >
            <span class="sr-only">Abrir menú principal</span>
            <svg
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
              />
            </svg>
          </button>
        </div>
        <div class="hidden lg:flex lg:gap-x-12">
          <a href="#" class="text-sm font-semibold text-gray-900">Inicio</a>
          <a href="#temas" class="text-sm font-semibold text-gray-900">Temas</a>
          <a href="#sobre-el-curso" class="text-sm font-semibold text-gray-900">Sobre el curso</a>
          <a href="#contacto" class="text-sm font-semibold text-gray-900">Contacto</a>
        </div>
        <div class="hidden lg:flex lg:flex-1 lg:justify-end">
          <a href="#" class="text-sm font-semibold text-gray-900"
            >Iniciar sesión <span aria-hidden="true">&rarr;</span></a
          >
        </div>
      </nav>
    </header>

    <!-- Hero Section -->
    <div class="relative isolate px-6 pt-14 lg:px-8">
      <div
        class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80"
        aria-hidden="true"
      >
        <div
          class="relative left-[calc(50%-11rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#ff80b5] to-[#9089fc] opacity-30 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
          style="
            clip-path: polygon(
              74.1% 44.1%,
              100% 61.6%,
              97.5% 26.9%,
              85.5% 0.1%,
              80.7% 2%,
              72.5% 32.5%,
              60.2% 62.4%,
              52.4% 68.1%,
              47.5% 58.3%,
              45.2% 34.5%,
              27.5% 76.7%,
              0.1% 64.9%,
              17.9% 100%,
              27.6% 76.8%,
              76.1% 97.7%,
              74.1% 44.1%
            );
          "
        ></div>
      </div>
      <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
        <div class="text-center">
          <h1 class="text-5xl font-bold text-gray-900 sm:text-6xl">
            Curso de Fundamentos de JavaScript
          </h1>
          <p class="mt-6 text-lg leading-8 text-gray-600">
            Aprende y repasa los conceptos esenciales de JavaScript, desde lo más básico hasta
            técnicas avanzadas, con ejemplos claros y ejercicios prácticos.
          </p>
          <div class="mt-10 flex items-center justify-center gap-x-6">
            <a
              href="#temas"
              class="rounded-md bg-indigo-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
              >Comenzar ahora</a
            >
            <a href="#sobre-el-curso" class="text-sm font-semibold text-gray-900"
              >Más información <span aria-hidden="true">→</span></a
            >
          </div>
        </div>
      </div>
    </div>

    <!-- Información adicional -->
    <div id="temas" class="bg-gray-100 py-16 px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-gray-900 mb-6">Temas que cubriremos</h2>
        <ul class="list-disc pl-6 text-lg text-gray-700">
          <li>Variables, Tipos de Datos y Operadores</li>
          <li>Funciones y Estructuras de Control</li>
          <li>Manejo del DOM y Eventos</li>
          <li>Programación Asíncrona y Promesas</li>
          <li>Introducción a APIs y Fetch</li>
        </ul>
      </div>
    </div>

    <div id="sobre-el-curso" class="py-16 px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-gray-900 mb-6">Sobre este curso</h2>
        <p class="text-lg text-gray-700">
          Este curso está diseñado tanto para principiantes como para aquellos que desean reforzar
          sus conocimientos en JavaScript. Cada lección incluye explicaciones claras, ejemplos
          interactivos y ejercicios prácticos para ayudarte a comprender los conceptos clave.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
/* Estilos opcionales adicionales */
</style>
