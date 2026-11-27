<template>
  <div class="mx-auto max-w-xl px-6 py-6 text-center" style="font-family: 'Prompt', sans-serif;">
    <div class="w-full h-min">
      <h2 class="text-xl font-semibold mb-2">ข้อมูลผู้ถูกประเมิน</h2>
      <p>ชื่อ-สกุล: {{ name }}</p>
      <p>ตำแหน่ง: {{ position }}</p>
      <p>แผนก: {{ department }}</p>
      <p>รอบการประเมิน: {{ period }}</p>
      <p>เบอร์โทรศัพท์: {{ phone }}</p>
    </div>
    <div class="mt-4">
      <h2 class="text-xl font-semibold mb-2">ผลการประเมิน</h2>
      <p>ความรับผิดชอบ: {{ responsibility }}</p>
      <p>การทำงานเป็นทีม: {{ teamwork }}</p>
      <p>การตรงต่อเวลา: {{ punctuality }}</p>
      <hr class="my-2" />
      <p><strong>คะแนนเฉลี่ย: {{ ((responsibility + teamwork + punctuality) / 3).toFixed(2) }}</strong></p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'ชวกร อ่อนสา',
      position: 'นักศึกษา',
      department: 'เทคโนโลยีสารสนเทศ',
      period: 'รอบประเมินที่ 2/2569',
      phone: '061-090-8914',
      responsibility: 4,
      teamwork: 3.5,
      punctuality: 4.5
    }
  }
}
</script>