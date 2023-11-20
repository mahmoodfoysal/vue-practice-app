<style scoped>
.setting-icon {
    text-align: center;
    font-size: 20px;
    border-radius: 50%;
    background: #F6F3FF;
    color: #A88DFA;
    vertical-align: middle;
    padding: 7px;
}

.search-icon {
    text-align: center;
    font-size: 20px;
    border-radius: 50%;
    background: #F6F3FF;
    color: #A88DFA;
    vertical-align: middle;
    padding: 7px;
}
.moon-icon {
    text-align: center;
    font-size: 20px;
    border-radius: 50%;
    background: #F6F3FF;
    color: #A88DFA;
    vertical-align: middle;
}

.notification-icon {
    text-align: center;
    font-size: 20px;
    border-radius: 50%;
    background: #F6F3FF;
    color: #A88DFA;
    vertical-align: middle;
    padding: 7px;
}
</style>
<template>
    <Disclosure as="nav" class="bg-[white] sticky top-0 z-40" v-slot="{ open }">
        <div class="mx-auto max-w-7xl px-2 sm:px-2">
            <div class="relative flex h-12 items-center justify-between">
                <div class="flex flex-shrink-0 items-center">
                    <h4 class="text-xl text-[#6518D8] font-bold">K-WD</h4>
                </div>
                <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
                    <!-- Mobile menu button-->
                    <DisclosureButton
                        class="relative inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
                        <span class="absolute -inset-0.5" />
                        <span class="sr-only">Open main menu</span>
                        <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
                        <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
                    </DisclosureButton>
                </div>
                <div class="flex flex-1 items-center justify-center sm:items-stretch lg:justify-end">

                    <div class="hidden sm:block">
                        <div class="flex space-x-4 flex-end">
                            <!-- <a v-for="item in navigation" :key="item.name" :href="item.href"
                                    :class="[item.current ? 'bg-gray-900 text-white' : 'text-[black] hover:bg-gray-700 hover:text-white', 'rounded-md px-3 py-2 text-sm font-medium']"
                                    :aria-current="item.current ? 'page' : undefined">
                                    <span class="material-icons">
                                        settings
                                    </span>
                                                    </a> -->

                        <span class="flex items-center">
                            <Switch v-model="enabled" :class="enabled ? 'bg-[#EDE9FE]' : 'bg-[#EDE9FE]'"
                                    class="relative inline-flex h-[25px] w-[50px] shrink-0 cursor-pointer rounded-full border-2 border-transparent transition-colors duration-200 ease-in-out focus:outline-none focus-visible:ring-2 focus-visible:ring-white/75">
                                    <span class="sr-only">Use setting</span>
                                    <span  aria-hidden="true" :class="enabled ? 'translate-x-7' : 'translate-x-0'" class="moon-icon material-icons pointer-events-none inline-block transform rounded-full bg-white shadow-lg ring-0 transition duration-200 ease-in-out">
                                        dark_mode
                                    </span>
                                    
                                </Switch>
                            </span>
                            <span class="material-icons hover:cursor-[pointer] notification-icon">
                                notifications
                            </span>
                            <span class="material-icons hover:cursor-[pointer] search-icon">
                                search
                            </span>
                            <span class="material-icons hover:cursor-[pointer] setting-icon">
                                settings
                            </span>

                        </div>
                    </div>
                </div>
                <div class="absolute inset-y-0 right-0 flex items-center sm:static sm:inset-auto">
                    <!-- <button type="button"
                                    class="relative rounded-full bg-gray-800 p-1 text-gray-400 hover:text-white focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                                    <span class="absolute -inset-1.5" />
                                    <span class="sr-only">View notifications</span>
                                    <BellIcon class="h-6 w-6" aria-hidden="true" />
                                </button> -->

                    <!-- Profile dropdown -->
                    <Menu as="div" class="relative ml-3">
                        <div>
                            <MenuButton
                                class="relative flex rounded-full bg-gray-800 text-sm focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                                <span class="absolute -inset-1.5" />
                                <span class="sr-only">Open user menu</span>
                                <img class="h-8 w-8 rounded-full"
                                    src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
                                    alt="" />
                            </MenuButton>
                        </div>
                        <transition enter-active-class="transition ease-out duration-100"
                            enter-from-class="transform opacity-0 scale-95" enter-to-class="transform opacity-100 scale-100"
                            leave-active-class="transition ease-in duration-75"
                            leave-from-class="transform opacity-100 scale-100"
                            leave-to-class="transform opacity-0 scale-95">
                            <MenuItems
                                class="absolute right-0 z-10 mt-2 w-48 origin-top-right rounded-md bg-white py-1 shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none">
                                <MenuItem v-slot="{ active }">
                                <a href="#"
                                    :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']">Your
                                    Profile</a>
                                </MenuItem>
                                <MenuItem v-slot="{ active }">
                                <a href="#"
                                    :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']">Settings</a>
                                </MenuItem>
                                <MenuItem v-slot="{ active }">
                                <a href="#"
                                    :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']">Sign
                                    out</a>
                                </MenuItem>
                            </MenuItems>
                        </transition>
                    </Menu>
                </div>
            </div>
        </div>

        <DisclosurePanel class="sm:hidden">
            <div class="space-y-1 px-2 pb-3 pt-2">
                <DisclosureButton v-for="item in navigation" :key="item.name" as="a" :href="item.href"
                    :class="[item.current ? 'bg-gray-900 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white', 'block rounded-md px-3 py-2 text-base font-medium']"
                    :aria-current="item.current ? 'page' : undefined">{{ item.name }}</DisclosureButton>
            </div>
        </DisclosurePanel>
    </Disclosure>
</template>
  
<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import { Bars3Icon, BellIcon, XMarkIcon } from '@heroicons/vue/24/outline'
import { ref } from 'vue'
import { Switch } from '@headlessui/vue'

const navigation = [
    { name: 'Home', href: '#', current: true },
    { name: 'District', href: '#', current: false },
    { name: 'Contact', href: '#', current: false },
    { name: 'About US', href: '#', current: false },
]


const enabled = ref(false)
</script>
