<script setup>
const search = ref('')
const students = ref([
  { id: 1, name: 'Itadori Yuji', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 2, name: 'Fuchiguro Megumi', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 3, name: 'Kugisaki Nobara', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 4, name: 'Zenin Maki', class: 'สทส.2/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 5, name: 'Inumaki Toge', class: 'สทส.2/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 6, name: 'Panda', class: 'สทส.2/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 7, name: 'Okkotsu Yuta', class: 'สทส.2/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 8, name: 'Hakari Kinji', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 9, name: 'Todo Aoi', class: 'สทส.1/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 10, name: 'Zenin Mai', class: 'สทส.1/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 11, name: 'Gojo Satoru', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 12, name: 'Geto Suguru', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 13, name: 'Fuchiguro Toji', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 14, name: 'Yuki Tsukumo', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 15, name: 'Zenin Naoya', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 16, name: 'Higuruma Hiromi', class: 'สทส.1/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 17, name: 'Takaba Fumihiko', class: 'สทส.1/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 18, name: 'Kashimo Hajime', class: 'สทส.1/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 19, name: 'Ryomen Sukuna', class: 'สทส.1/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 20, name: 'Kenjaku', class: 'สทส.1/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 21, name: 'Gege Akutami', class: 'สทส.2/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 22, name: 'Kusakabe Atsuya', class: 'สทส.2/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 23, name: 'Kasumi Miwa', class: 'สทส.1/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 24, name: 'Kiyotaka Ljichi', class: 'สทส.2/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 26, name: 'Mei Mei', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 27, name: 'Mahito', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 28, name: 'Negi Yoshino', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 29, name: 'Masamichi Yaga', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 30, name: 'Shoko Ieiri', class: 'สทส.2/1', program: 'เทคโนโลยีสารสนเทศ' },
])
const filteredStudents = computed(() =>
  students.value.filter(student =>
    student.name.toLowerCase().includes(search.value.toLowerCase())
  )
)
</script>

<template>
  <div class="student-page">
    <h1 class="page-title">ข้อมูลนักเรียน</h1>

    <input
      v-model="search"
      type="text"
      placeholder="ค้นหาชื่อนักเรียน..."
      class="search-box"
    />

    <table class="student-table">
      <thead>
        <tr>
          <th>ลำดับ</th>
          <th>ชื่อ-นามสกุล</th>
          <th>ห้อง</th>
          <th>แผนการเรียน</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="student in filteredStudents" :key="student.id">
          <td>{{ student.id }}</td>
          <td>{{ student.name }}</td>
          <td>{{ student.class }}</td>
          <td>{{ student.program }}</td>

        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
.student-page {
  padding: 2rem;
  background-color: #111;
  color: white;
}

.page-title {
  font-size: 1.8rem;
  color: #008f0c;
  margin-bottom: 1rem;
  text-align: center;
}

.search-box {
  width: 100%;
  max-width: 400px;
  padding: 0.75rem 1rem;
  margin: 0 auto 2rem;
  display: block;
  border-radius: 8px;
  border: none;
  background-color: #222;
  color: white;
  font-size: 1rem;
}

.search-box::placeholder {
  color: #888;
}

.student-table {
  width: 100%;
  border-collapse: collapse;
  background-color: #222;
  border-radius: 10px;
  overflow: hidden;
}

.student-table th,
.student-table td {
  padding: 1rem;
  border-bottom: 1px solid #333;
  text-align: left;
}

.student-table th {
  background-color: #333;
  color: #008f0c;
}

.student-table tr:hover {
  background-color: #2a2a2a;
}
</style>
