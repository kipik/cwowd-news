<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
        <header class="h-16 bg-primary-content shadow">
            <div class="navbar bg-primary-content shadow-sm">
                <div class="navbar-start">
                    <div class="dropdown">
                        <div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M4 6h16M4 12h8m-8 6h16" />
                            </svg>
                        </div>
                        <ul tabindex="0"
                            class="menu menu-sm dropdown-content bg-base-100 rounded-box z-1 mt-3 w-52 p-2 shadow navbar-list space-x-6">
                            <li><a href="#" class="navbar-list-link">Accueil</a></li>
                            <li><a href="#" class="navbar-list-link">Articles</a></li>
                            <li><a href="#" class="navbar-list-link">Publications</a></li>
                            <li><a href="#" class="navbar-list-link">Paroles</a></li>
                            <li><a href="#" class="navbar-list-link">On en discute</a></li>
                        </ul>
                    </div>
                    <a class="btn btn-ghost text-2xl font-bold">Cwowd.com</a>
                </div>
                <div class="navbar-center hidden lg:flex">
                    <ul class="menu menu-horizontal px-1">
                        <li><a href="#" class="navbar-list-link">Accueil</a></li>
                        <li><a href="#" class="navbar-list-link">Articles</a></li>
                        <li><a href="#" class="navbar-list-link">Publications</a></li>
                        <li><a href="#" class="navbar-list-link">Paroles</a></li>
                        <li><a href="#" class="navbar-list-link">On en discute</a></li>
                    </ul>
                </div>
                <div class="navbar-end">
                    <label class="input">
                        <Input id="search" type="text" placeholder="On cherche quoi?" class="pl-10" />
                        <span class="absolute start-0 inset-y-0 flex items-center justify-center px-2">
                            <Search class="size-6 text-muted-foreground" />
                        </span>
                    </label>
                    <button class="btn btn-ghost btn-circle">
                        <div class="indicator">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
                            </svg>
                            <span class="badge badge-xs badge-primary indicator-item" />
                        </div>
                    </button>
                </div>
            </div>
        </header>
    </div>
</template>

<script setup lang="ts">
import { Input } from '@/components/ui/input'
import { Search } from 'lucide-vue-next'
</script>
