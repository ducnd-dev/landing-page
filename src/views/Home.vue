<template>
  <div class="home container mt-[160vh]">
    <div>
        <div>
            <div class="text-center mx-auto lg:w-[55%]">
                <h2 class="text-5xl font-semibold text-black">
                  <vue-typer :text="['Mang đến giải pháp toàn diện cho doanh nghiệp của bạn']" type-speed="100" back-speed="100" back-delay="1000"  />
                </h2>
                <p class="text-xl font-medium mt-5">GATE mang đến cho doanh nghiệp khả năng kiểm soát hiệu quả bán hàng từ các chiến dịch quảng cáo trở nên nhanh chóng hơn, trực quan hơn và chính xác hơn bằng cách đồng bộ dữ liệu từ các nền tảng CRM và nền tảng quảng cáo vào 1 trang duy nhất</p>
            </div>
        </div>
        <div class="mt-32">
          <div class="grid grid-cols-2 gap-5 ">
            <div v-for="(item, i) in solutions" :key="i" :class="i == 0 ? 'col-span-full grid lg:grid-cols-2 gap-4 p-5': 'col-span-1'" class="bg-white rounded-2xl">
              <div class="order-2">
                <div class="p-4" data-aos="fade-up" data-aos-duration="1500" data-aos-anchor-placement="center-center">
                  <img :src="item.thumbnail" alt="icon" class="object-cover w-full" />
                </div>
              </div>
              <div class="p-4 lg:p-12">
                <h3 class="text-2xl font-semibold mt-4" data-aos="fade-up" data-aos-duration="1500">{{ item.title }}</h3>
                <p class="mt-2"  data-aos="fade-up" data-aos-duration="1500" >{{ item.description }}</p>
                <ul class="mt-4">
                  <li v-for="(list, i) in item.list" :key="i" class="flex items-center gap-2 h-8">
                    <img src="../assets/circle-plus.svg" alt="icon" class="w-5 h-5" />
                    <span data-aos="fade-up" data-aos-duration="1500">{{ list.title }}</span>
                  </li>
                </ul>
                <div class="flex items-center gap-2 mt-4 lg:mt-10">
                  <button v-if="item.isTrial" class=" bg-blue-500 text-whitep-2  rounded-full text-white flex items-center gap-3 p-2">
                    <img src="../assets/circle-insert.svg" /> Dùng thử 
                  </button>
                  <button class="border p-3 rounded-full flex gap-3 items-center">
                    <img src="../assets/circle-plus.svg" />
                    Đọc chi tiết</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div>
        <div class="text-center mt-20">
          <h2 class="text-5xl font-semibold">Giá trị mà bạn sẽ nhận được</h2>
          <p class="text-xl font-medium mt-5">Our Advanced Settings & Integration Tools are designed to provide maximum flexibility and control over your system’s functionality.</p>
        </div>
       <bottom />
      </div>
  </div>
</template>

<script>
import { VueTyper } from 'vue-typer';

import img from '../assets/solution-demo.png';
export default {
  name: 'Home',
  components: {
    VueTyper,
  },
  data() {
    return {
      solutions: [
        {
          title: 'Báo cáo hiệu suất toàn diện',
          description: 'Báo cáo hiệu suất quảng cáo, nhân sự, kinh doanh bằng các tích hợp CRM và dữ liệu quảng cáo',
          isTrial: true,
          thumbnail: img,
          list: [
            {
              icon: 'icon',
              title: 'Báo cáo quảng cáo',
            },
            {
              icon: 'icon',
              title: 'Dashboard',
            },
          ],
        },
        {
          title: 'Báo cáo hiệu suất toàn diện',
          isTrial: true,
          thumbnail: img,
          list: [
            {
              icon: 'icon',
              title: 'Báo cáo quảng cáo',
            },
            {
              icon: 'icon',
              title: 'Dashboard',
            },
          ],
        },
        {
          title: 'Báo cáo hiệu suất toàn diện',
          isTrial: true,
          thumbnail: img,
          list: [
            {
              icon: 'icon',
              title: 'Báo cáo quảng cáo',
            },
            {
              icon: 'icon',
              title: 'Dashboard',
            },
          ],
        },
        {
          title: 'Báo cáo hiệu suất toàn diện',
          isTrial: true,
          thumbnail: img,
          list: [
            {
              icon: 'icon',
              title: 'Báo cáo quảng cáo',
            },
            {
              icon: 'icon',
              title: 'Dashboard',
            },
          ],
        },
        {
          title: 'Báo cáo hiệu suất toàn diện',
          isTrial: true,
          thumbnail: img,
          list: [
            {
              icon: 'icon',
              title: 'Báo cáo quảng cáo',
            },
            {
              icon: 'icon',
              title: 'Dashboard',
            },
          ],
        },
      ],
    };
  },
};
</script>
