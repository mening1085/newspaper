<script setup>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";
const darkMode = ref(false);

onMounted(() => {
  watchEffect(() => {
    if (darkMode.value) {
      document.documentElement.classList.add("dark");
    } else {
      document.documentElement.classList.remove("dark");
    }
  });
});
</script>

<template>
  <div class="dark:bg-black bg-white dark:text-white min-h-screen">
    <div
      class="container mx-auto shadow-lg rounded my-12 p-3 bg-zinc-100 news__paper"
    >
      <!-- Sectin About me -->
      <div class="grid grid-cols-2 overflow-hidden">
        <img
          src="./assets/images/avatar.JPG"
          alt=""
          class="h-[675px] object-cover w-full"
        />
        <div>
          <div class="bg_green px-2">
            <div class="text-[85px] font-bold uppercase text-white">
              Mr.Kasem Tanson
            </div>
            <div class="text-[62px] -mt-8 text-gray-900">
              หนุ่มสุดงง นอนเล่นเกมอยู่ดีๆ
            </div>
            <div class="flex flex-wrap items-end -mt-8 gap-4">
              <div class="text-[68px] pb-3 text-gray-900">กลายมาเป็น</div>
              <div class="text-[98px] font-bold text-white">Fullstack</div>
              <div class="text-[98px] font-bold -mt-16 text-white">
                Developer
              </div>
              <span class="text-[74px] pb-2 -mt-16 text-gray-900">
                ได้ยังไง ?
              </span>
            </div>
          </div>

          <div class="grid grid-cols-3 py-2 gap-2">
            <div class="border-r-2 border-black px-2">
              <div>
                สวัสดี! ผมชื่อ เกษม แท่นสอน (เม่น)
                ผมเป็นนักพัฒนาเว็บไซต๋ที่หลงใหลในเทคโนโลยีและชอบเรียนรู้เกี่ยวกับเทคโนโลยีอยู่เสมอ
              </div>

              <div>
                <span class="text-red-600">บุคคลิก/ลักษณะนิสัย :</span>
                ภายนอกอาจจะดูเงียบๆ แต่ที่จริงเป็นคนเข้ากับคนอื่นง่าย ร่าเริง
                ชอบเฮฮา ปาร์ตี้
              </div>
              <div>
                <span class="text-red-600">งานอดิเรก/เวลาว่าง :</span>
                ถ่ายรูป ท่องเที่ยว ดูหนัง เล่นเกม ออกกำลังกาย
                อัพเดทข่าวสารของเทคโนโลยีต่างๆ หรือการพัฒนาเว็บไซต์อยู่เสมอ
              </div>
            </div>

            <div class="px-2 border-r-2 border-black">
              <div>
                <span class="text-red-600 text-[24px] font-bold"
                  >Education</span
                >
              </div>
              <div>มหาวิทยาลัยนเรศวร คณะวิทยาศาสตร์ สาขาเทคโนโลยี</div>
              <div>
                <div class="text-red-600 text-[24px] font-bold">Experience</div>
                <ul>
                  <li>
                    - <span class="font-bold">PHP Developer (Intern)</span> :
                    TARAD.com (2019)
                  </li>
                  <li>
                    - <span class="font-bold">Full-Stack Developer</span> :
                    Kisra Corp (2020 - 2023)
                  </li>
                  <li>
                    -
                    <span class="font-bold">Senior Full-Stack Developer</span> :
                    Kisra Corp (2023 - Present)
                  </li>
                </ul>
              </div>
            </div>

            <div class="px-2">
              I am a Full stack developer, Every day I always think that I don't
              just come to work to make money. But I'm here to create a work.
              Because working in the world of programming isn't just a job. But
              it was also an exciting adventure. Full of technology that is
              constantly changing.
            </div>
          </div>
        </div>
      </div>

      <div class="grid grid-cols-3 overflow-hidden">
        <div class="col-span-2">
          <div class="bg_green text-[77px] font-bold uppercase text-white p-2">
            สุดช็อค! ทำงานเยอะจนลืมดูเวลา รู้ตัวอีกที นี่ผ่านมา 5 ปีแล้วหรอ ?
          </div>
        </div>
        <div>
          <carousel :items-to-show="1" :autoplay="2000" :wrap-around="true">
            <slide v-for="slide in 10" :key="slide">
              <img
                src="./assets//images/project/DITP/f/Home 2.jpg"
                class="h-[400px] object-cover w-full"
                alt=""
              />
            </slide>
          </carousel>
        </div>
      </div>
    </div>

    <!-- add button to switch mode -->
    <button class="btn_mode" @click="darkMode = !darkMode">Switch Mode</button>
  </div>
</template>

<style lang="scss">
.news__paper {
}
.btn_mode {
  position: fixed;
  bottom: 20px;
  right: 20px;
  padding: 10px 20px;
  background-color: #000;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
</style>
