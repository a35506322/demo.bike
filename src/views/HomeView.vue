<script setup>
import { ref, onMounted } from 'vue';
import { initFlowbite } from 'flowbite';

// initialize components based on data attribute selectors
onMounted(() => {
  initFlowbite();
});

/*
"sno"：站點編號，這裡是 500101001。
"sna"：站點名稱，中文為 YouBike2.0_捷運科技大樓站。
"sarea"：站點所在區域，這裡位於大安區。
"mday"：資料更新時間，是在 2024 年 5 月 11 日晚上 20:15:19 更新的。
"ar"：站點地址，這裡是在復興南路二段235號前。
"sareaen"：站點所在區域的英文名稱，是 Daan Dist.。
"snaen"：站點名稱的英文翻譯，是 YouBike2.0_MRT Technology Bldg. Sta.。
"aren"：站點地址的英文翻譯，是 No.235， Sec. 2， Fuxing S. Rd.。
"act"：站點是否在使用中，這裡是 1 代表在使用中。
"srcUpdateTime"：原始資料來源的更新時間，是在 2024 年 5 月 11 日晚上 20:15:26 更新的。
"updateTime"：資料更新時間，是在 2024 年 5 月 11 日晚上 20:15:52。
"infoTime"：資訊時間，是在 2024 年 5 月 11 日晚上 20:15:19。
"infoDate"：資訊日期，是在 2024 年 5 月 11 日。
"total"：總車位數量，這裡是 28 個。
"available_rent_bikes"：可租借的腳踏車數量，這裡是 1 輛。
"latitude"：站點的緯度坐標，這裡是 25.02605。
"longitude"：站點的經度坐標，這裡是 121.5436。
"available_return_bikes"：可歸還的腳踏車數量，這裡是 27 輛。
*/
const bikeinfo = ref([
  {
    sno: '500101001',
    sna: 'YouBike2.0_捷運科技大樓站',
    sarea: '大安區',
    mday: '2024-05-11 20:15:19',
    ar: '復興南路二段235號前',
    sareaen: 'Daan Dist.',
    snaen: 'YouBike2.0_MRT Technology Bldg. Sta.',
    aren: 'No.235， Sec. 2， Fuxing S. Rd.',
    act: '1',
    srcUpdateTime: '2024-05-11 20:15:26',
    updateTime: '2024-05-11 20:15:52',
    infoTime: '2024-05-11 20:15:19',
    infoDate: '2024-05-11',
    total: 28,
    available_rent_bikes: 1,
    latitude: 25.02605,
    longitude: 121.5436,
    available_return_bikes: 27
  }
]);
</script>

<template>
  <div class="container mx-auto px-4">
    <!--top bar start-->
    <nav
      class="bg-white dark:bg-gray-900 fixed w-full z-20 top-0 start-0 border-b border-gray-200 dark:border-gray-600"
    >
      <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
        <a href="https://flowbite.com/" class="flex items-center space-x-3 rtl:space-x-reverse">
          <img src="https://flowbite.com/docs/images/logo.svg" class="h-8" alt="Flowbite Logo" />
          <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white"
            >YouBike範本</span
          >
        </a>
        <div class="flex md:order-2 space-x-3 md:space-x-0 rtl:space-x-reverse">
          <div class="mr-2">
            <input
              type="text"
              id="first_name"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
              placeholder="輸入關鍵字查詢"
              required
            />
          </div>
          <button
            type="submit"
            class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center cursor-pointer"
          >
            查詢
          </button>
        </div>
      </div>
    </nav>
    <!--top bar end-->
    <!--datatable start-->
    <div class="relative overflow-x-auto shadow-md top-20">
      <table class="w-full text-sm text-left rtl:text-right text-gray-500 dark:text-gray-400">
        <thead class="text-white uppercase bg-blue-600 dark:text-white">
          <tr>
            <th class="font-semibold text-center p-2">站點編號</th>
            <th class="font-semibold text-center p-2">站點名稱</th>
            <th class="font-semibold text-center p-2">站點所在區域</th>
            <th class="font-semibold text-center p-2">站點地址</th>
            <th class="font-semibold text-center p-2">總車位數量</th>
            <th class="font-semibold text-center p-2">可租借的腳踏車數量</th>
            <th class="font-semibold text-center p-2">站點緯度</th>
            <th class="font-semibold text-center p-2">站點經度</th>
            <th class="font-semibold text-center p-2">可歸還的腳踏車數量</th>
          </tr>
        </thead>
        <tbody>
          <tr
            class="odd:bg-white odd:dark:bg-gray-900 even:bg-gray-50 even:dark:bg-gray-800 border-b dark:border-gray-700 hover:bg-blue-100"
          >
            <td class="p-2 text-center">{{ bikeinfo[0].sno }}</td>
            <td class="p-2 text-center">{{ bikeinfo[0].sna }}</td>
            <td class="p-2 text-center">{{ bikeinfo[0].sarea }}</td>
            <td class="p-2 text-center">{{ bikeinfo[0].ar }}</td>
            <td class="p-2 text-center">{{ bikeinfo[0].total }}</td>
            <td class="p-2 text-center">{{ bikeinfo[0].available_rent_bikes }}</td>
            <td class="p-2 text-center">{{ bikeinfo[0].latitude }}</td>
            <td class="p-2 text-center">{{ bikeinfo[0].longitude }}</td>
            <td class="p-2 text-center">{{ bikeinfo[0].available_return_bikes }}</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!--datatable end-->
  </div>
</template>
