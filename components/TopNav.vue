<script setup>
const route = useRoute();
let showMenu = ref(false);
</script>

<template>
  <div
    id="TopNav"
    class="bg-white z-30 flex items-center w-full border-b h-[61px]"
  >
    <div
      :class="route.fullPath === '/' ? 'max-w-[1150px]' : ''"
      class="flex items-center justify-between w-full px-6 mx-auto"
    >
      <div :class="route.fullPath === '/' ? 'w-[80%]' : 'lg:w-[70%]'">
        <NuxtLink to="/">
          <img src="~/assets/images/tiktok-logo.png" alt="" width="115"
        /></NuxtLink>
      </div>
      <div
        class="hidden md:flex items-center bg-[#F1F1F2] rounded-full max-w-[380px] w-full"
      >
        <input
          type="text"
          class="w-full px-3 py-1 bg-transparent placeholder-[#838383] text-[15px] focus:outline-none"
          placeholder="Search accounts"
        />
        <div class="p-1 flex items-center justify-center">
          <Icon size="22" name="material-symbols:search-rounded" />
        </div>
      </div>
      <div
        class="flex items-center justify-end gap-3 min-w-[275px] max-w-[320px] w-full"
      >
        <button
          class="flex justify-center items-center border rounded-md px-3 py-[6px] hover:bg-gray-100"
        >
          <Icon name="ep:plus" color="#00000" size="22" />
          <span class="px-2 font-medium text-[15px]">Upload</span>
        </button>
        <div class="flex items-center" v-if="false">
          <button
            class="flex items-center bg-red-600 text-white border rounded-md px-3 py-[6px]"
          >
            <span class="text-nowrap">Log In</span>
          </button>
          <Icon name="mdi:dots-vertical" size="25" />
        </div>
        <div class="flex items-center">
          <Icon
            name="carbon:send-alt"
            color="#161724"
            size="25"
            class="ml-1 mr-4"
          />
          <Icon name="bx:message-detail" size="25" class="mr-5" />
          <div>
            <button class="mt-1" @click="($event) => (showMenu = !showMenu)">
              <img
                class="rounded-full"
                width="33"
                src="https://picsum.photos/id/83/300/320
            "
              />
            </button>
            <div
              v-if="showMenu"
              id="popupMenu"
              class="absolute rounded-lg py-1.5 w-[200px] shadow-xl border top-[43px -right-2 bg:white]"
            >
              <NuxtLink
                @click="($event) => (showmenu = false)"
                to=""
                class="flex items-center justify-start py-3 px-2 hover:bg-gray-100 cursor-pointer"
                ><Icon name="ph:user" size="'20" /><span
                  class="pl-2 font-semi-bold text-sm"
                  >Profile</span
                >
              </NuxtLink>

              <NuxtLink
                @click="($event) => (showmenu = false)"
                to=""
                class="flex items-center justify-start py-3 px-1.5 hover:bg-gray-100 cursor-pointer border-t"
                ><Icon name="ic:outline-login" size="'20" /><span
                  class="pl-2 font-semi-bold text-sm"
                  >Log Out</span
                >
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
