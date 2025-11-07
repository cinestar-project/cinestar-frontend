<script setup>
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
  navigationMenuTriggerStyle,
} from "@/components/ui/navigation-menu"
</script>

<template>
  <header class="sticky top-0 z-50 w-full border-b border-amber-200 bg-white/95 backdrop-blur supports-[backdrop-filter]:bg-white/80">
    <!-- Mudei: removi 'container' e usei 'w-full max-w-none' + mx-auto para controlar o padding -->
    <div class="w-full flex h-16 items-center justify-between px-6 lg:px-12">
      <!-- Logo -->
      <a href="/" class="flex items-center gap-2">
        <img src="@/assets/logo.png" alt="CineStar Logo" class="h-10 w-10 object-contain">
        <span class="text-xl font-bold text-amber-600">CineStar</span>
      </a>

      <!-- Navigation Menu -->
      <NavigationMenu class="hidden md:flex">
        <NavigationMenuList>
          <!-- Início -->
          <NavigationMenuItem>
            <NavigationMenuLink href="/" :class="navigationMenuTriggerStyle()">
              Início
            </NavigationMenuLink>
          </NavigationMenuItem>

          <!-- Filmes -->
          <NavigationMenuItem>
            <NavigationMenuLink href="/filmes" :class="navigationMenuTriggerStyle()">
              Filmes
            </NavigationMenuLink>
          </NavigationMenuItem>

          <!-- Em Breve -->
          <NavigationMenuItem>
            <NavigationMenuTrigger class="text-amber-700 hover:text-amber-600">
              Em Breve
            </NavigationMenuTrigger>
            <NavigationMenuContent>
              <ul class="grid gap-3 p-6 md:w-[400px] lg:w-[500px] lg:grid-cols-[minmax(0,.75fr)_minmax(0,1fr)]">
                <li class="row-span-3">
                  <NavigationMenuLink as-child>
                    <a
                      class="flex h-full w-full select-none flex-col justify-end rounded-md bg-gradient-to-b from-amber-100 to-amber-200 p-6 no-underline outline-none focus:shadow-md"
                      href="/em-breve"
                    >
                      <div class="h-12 w-12 rounded-full bg-amber-500 flex items-center justify-center mb-2">
                        <span class="text-2xl">🍿</span>
                      </div>
                      <div class="mb-2 mt-4 text-lg font-medium text-amber-900">
                        Próximas Estreias
                      </div>
                      <p class="text-sm leading-tight text-amber-700">
                        Descobre os filmes que estão prestes a estrear no CineStar.
                      </p>
                    </a>
                  </NavigationMenuLink>
                </li>

                <li>
                  <NavigationMenuLink as-child>
                    <a
                      href="/em-breve"
                      class="block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-amber-50 hover:text-amber-900 focus:bg-amber-50 focus:text-amber-900"
                    >
                      <div class="text-sm font-medium leading-none text-amber-800">Ver Todos</div>
                      <p class="line-clamp-2 text-sm leading-snug text-amber-600">
                        Consulta o calendário completo de estreias.
                      </p>
                    </a>
                  </NavigationMenuLink>
                </li>
              </ul>
            </NavigationMenuContent>
          </NavigationMenuItem>

          <!-- Sessões -->
          <NavigationMenuItem>
            <NavigationMenuLink href="/sessoes" :class="navigationMenuTriggerStyle()">
              Sessões
            </NavigationMenuLink>
          </NavigationMenuItem>
        </NavigationMenuList>
      </NavigationMenu>

      <!-- Pesquisa + Login/Avatar -->
      <div class="flex items-center gap-3">
        <!-- Barra de Pesquisa -->
        <button class="hidden md:flex items-center gap-2 rounded-md border border-amber-200 px-3 py-2 text-sm text-amber-700 hover:bg-amber-50">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
          </svg>
          <span>Procurar...</span>
        </button>

        <!-- Botão de Login -->
        <a href="/login" class="inline-flex items-center justify-center rounded-md bg-amber-500 px-4 py-2 text-sm font-medium text-white hover:bg-amber-600 transition-colors">
          Entrar
        </a>
      </div>
    </div>
  </header>
</template>
