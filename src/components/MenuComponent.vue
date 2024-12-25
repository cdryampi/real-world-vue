<template>
  <header class="absolute inset-x-0 top-0 z-50 bg-white">
    <nav
      class="mx-auto flex max-w-7xl items-center justify-between p-6 lg:px-8"
      aria-label="Global"
    >
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
          @click="mobileMenuOpen = true"
        >
          <span class="sr-only">Abrir menú principal</span>
          <Bars3Icon class="h-6 w-6" aria-hidden="true" />
        </button>
      </div>
      <PopoverGroup class="hidden lg:flex lg:gap-x-12">
        <Popover class="relative">
          <PopoverButton class="flex items-center gap-x-1 text-sm font-semibold text-gray-900">
            Recursos
            <ChevronDownIcon class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
          </PopoverButton>

          <transition
            enter-active-class="transition ease-out duration-200"
            enter-from-class="opacity-0 translate-y-1"
            enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition ease-in duration-150"
            leave-from-class="opacity-100 translate-y-0"
            leave-to-class="opacity-0 translate-y-1"
          >
            <PopoverPanel
              class="absolute -left-8 top-full z-10 mt-3 w-screen max-w-md overflow-hidden rounded-3xl bg-white shadow-lg ring-1 ring-gray-900/5"
            >
              <div class="p-4">
                <div
                  v-for="item in resources"
                  :key="item.name"
                  class="group relative flex items-center gap-x-6 rounded-lg p-4 text-sm hover:bg-gray-50"
                >
                  <div
                    class="flex h-11 w-11 flex-none items-center justify-center rounded-lg bg-gray-50 group-hover:bg-white"
                  >
                    <component
                      :is="item.icon"
                      class="h-6 w-6 text-gray-600 group-hover:text-indigo-600"
                      aria-hidden="true"
                    />
                  </div>
                  <div class="flex-auto">
                    <a :href="item.href" class="block font-semibold text-gray-900">
                      {{ item.name }}
                      <span class="absolute inset-0" />
                    </a>
                    <p class="mt-1 text-gray-600">{{ item.description }}</p>
                  </div>
                </div>
              </div>
            </PopoverPanel>
          </transition>
        </Popover>
        <a href="#" class="text-sm font-semibold text-gray-900">Lecciones</a>
        <a href="#" class="text-sm font-semibold text-gray-900">Ejercicios</a>
        <a href="#" class="text-sm font-semibold text-gray-900">Proyectos</a>
      </PopoverGroup>
      <div class="hidden lg:flex lg:flex-1 lg:justify-end">
        <a href="#" class="text-sm font-semibold text-gray-900">Iniciar sesión &rarr;</a>
      </div>
    </nav>
    <Dialog class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
      <div class="fixed inset-0 z-10" />
      <DialogPanel
        class="fixed inset-y-0 right-0 z-10 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10"
      >
        <div class="flex items-center justify-between">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only">Fundamentos de JavaScript</span>
            <img
              class="h-8 w-auto"
              src="https://tailwindui.com/plus/img/logos/mark.svg?color=indigo&shade=600"
              alt="Logo"
            />
          </a>
          <button
            type="button"
            class="-m-2.5 rounded-md p-2.5 text-gray-700"
            @click="mobileMenuOpen = false"
          >
            <span class="sr-only">Cerrar menú</span>
            <XMarkIcon class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        <div class="mt-6 flow-root">
          <div class="-my-6 divide-y divide-gray-500/10">
            <div class="space-y-2 py-6">
              <a
                v-for="item in menuItems"
                :key="item.name"
                :href="item.href"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold text-gray-900 hover:bg-gray-50"
              >
                {{ item.name }}
              </a>
            </div>
            <div class="py-6">
              <a
                href="#"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold text-gray-900 hover:bg-gray-50"
              >
                Iniciar sesión
              </a>
            </div>
          </div>
        </div>
      </DialogPanel>
    </Dialog>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import {
  Dialog,
  DialogPanel,
  Popover,
  PopoverButton,
  PopoverGroup,
  PopoverPanel,
} from '@headlessui/vue'

import {
  Bars3Icon,
  ChartPieIcon,
  CursorArrowRaysIcon,
  SquaresPlusIcon,
  XMarkIcon,
} from '@heroicons/vue/24/outline'

import { ChevronDownIcon } from '@heroicons/vue/20/solid'

const mobileMenuOpen = ref(false)

const resources = [
  {
    name: 'Variables y Tipos',
    description: 'Conceptos básicos de JavaScript',
    href: '#',
    icon: ChartPieIcon,
  },
  {
    name: 'Funciones',
    description: 'Cómo crear y usar funciones',
    href: '#',
    icon: CursorArrowRaysIcon,
  },
  { name: 'DOM', description: 'Interacción con el DOM', href: '#', icon: SquaresPlusIcon },
]

const menuItems = [
  { name: 'Lecciones', href: '#' },
  { name: 'Ejercicios', href: '#' },
  { name: 'Proyectos', href: '#' },
]
</script>

<script>
export default {
  name: 'MenuComponent',
}
</script>
