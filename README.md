# JavaScript Framework (VueJS) 2 - To Do App - Component -Tazkia
Folder ini merupakan task kedua dari materi JavaScript Framework. JavaScript framework yang digunakan adalah VueJS, sementara untuk styling digunakan CSS framework yaitu Bootstrap. 

## Getting started
1. Download atau clone repository ini :
```
git clone https://github.com/tazkiaathariza/btj-academy-fe-vue-todo-component-tazkia
```
2. Install seluruh dependencies yang diperlukan.
2. Jalankan `npm run dev`
3. Buka di browser lokal `http://127.0.0.1:5173/`

## Building
### Component
1. `Button.vue` : Inject function dari App.vue untuk handleClick. Memiliki props 'buttonName'. Dengan menggunakan switch-case,'buttonName' akan menentukan class styling dan fungsi (handleClick) yang dimiliki oleh button tersebut ketika digunakan oleh komponen lain.
2. `CountCard.vue` : Merupakan template card yang memiliki props 'countName' dan 'countNumber'. 
3. `CountPriority.vue` : Menampilkan perhitungan jumlah task berdasarkan prioritas. Menggunakan komponen 'CountCard' sebagai template.
4. `Done.vue` : Menampilkan seluruh task yang sudah selesai. Memiliki props 'taskDone' yang merupakan array.
5. `InputForm.vue` : Merupakan form untuk menambahkan task. Memiliki props 'addTaskList' yang merupakan function dan 'newTask' yang merupakan object.
6. `Task.vue` : Menampilkan task apa saja yang belum selesai. Memiliki props 'taskDone' yang merupakan array.
7. `Title.vue` : Template judul.
### App
`App.vue` merupakan main file yang menggunakan dan menyusun komponen-komponen utama. Pada file ini juga terdapat provide, methods, computed, etc.

## What you can do in this TODO App
1. Menambahkan task baru yang akan disimpan di dalam local storage.
2. Menampilkan seluruh task yang belum selesai pada kolom 'TODO'.
3. Menandai task yang sudah selesai dengan tombol 'Done'.
4. Menampilan seluruh task yang sudah selesai pada kolom 'DONE'.
5. Menghapus task dari list 'TODO' maupun 'DONE'.
6. Melakukan 'Undone'.
7. Menghitung jumlah task dengan priority 'medium', 'high', 'low', dan'pending'.