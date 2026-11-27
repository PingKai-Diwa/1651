<template>
  <div class="w-full  bg-amber-50/30" style="font-family: 'Prompt', sans-serif;">
    <!-- Navbar (แถบเมนูสีเหลืองทองสง่างาม) -->
    <nav class="bg-amber-500 text-amber-950 shadow-xl fixed top-0 left-0 w-full z-50 border-b-2 border-amber-600">
      <div class="w-full flex justify-between items-center px-10 py-4">
        
        <!-- โลโก้และชื่อระบบ (ฝั่งซ้าย) -->
        <a href="#" class="flex items-center space-x-3">
          <img src="../assets/icon.png" alt="Logo" class="h-10 w-10 object-contain rounded-lg shadow-sm" />
          <span class="text-2xl font-bold text-amber-950 tracking-wide">ระบบประเมินบุคลากร</span>
        </a>


        <!-- เมนูนำทาง (ตรงกลาง) -->
        <ul class="hidden md:flex space-x-6 text-amber-950 font-bold">
          <li><a href="#" class="px-4 py-2 hover:bg-amber-400 rounded-lg transition-colors duration-200">หน้าแรก</a></li>
          <li><a href="#" class="px-4 py-2 hover:bg-amber-400 rounded-lg transition-colors duration-200">แบบประเมิน</a></li>
          <li><a href="#" class="px-4 py-2 hover:bg-amber-400 rounded-lg transition-colors duration-200">รายงานผล</a></li>
          <li><a href="#" class="px-4 py-2 hover:bg-amber-400 rounded-lg transition-colors duration-200">ผู้ใช้</a></li>
        </ul>


        <!-- ปุ่ม Sign In / Sign Up (ฝั่งขวาสุด) -->
        <div class="hidden md:flex space-x-3">
          <a href="#" class="px-4 py-2 bg-amber-600 hover:bg-amber-700 text-white rounded-lg font-bold transition-colors duration-200 shadow-sm">
            Sign In
          </a>
          <a href="#" class="px-4 py-2 bg-red-700 hover:bg-red-800 text-white rounded-lg font-bold transition-colors duration-200 shadow-md">
            Sign Up
          </a>
        </div>


      </div>
    </nav>


    
  </div>
</template>


<script>
export default {
  name: 'MyBar'
}
</script>


<style scoped>
</style>