# modul4

Pengurutan / Sorting
Proses pengurutan merupakan salah satu proses yang sangat penting dalam pengolahan data.
Misalkan terdapat data mahasiswa, terkadang dibutuhkan data yang urut berdasarkan nilai, penghasilan orang tua,
sehingga dari data yang urut tersebut dapat diambil keputusan mengenai mahasiswa yang berhak menerima beasiswa.
proses pengurutan data ini dilakukan dengan membandingkan antara data yang satu dengan data yang lain.


Bubble Sort
merupakan proses pengurutan yang secara berangsur-angsur berpindah ke posisi yang tepatkarena itulah dinamakan Bubble
yang artinya gelembung.

Bubble sort mengurutkan data dengan cara sebagai berikut :
  1. data dibaca mulai dari paling kiri atau mulai dari indeks ke 0 (phyton) dari suatu list data
  2. Bandingkan antara dua buah data yang saling berdekatan (antara data ke i dan i+1),
     tukar posisi jika data ke-i lebih besar dibandingkan data ke-i+1 (pengurutan secara ascending)
  3. pindah satu posisi
  4. lakukan perbandingan seperti langkah ke-2 dan pindah satu posisi kembali seperti langkah ke-3.
     Lakukan terus menerus sampai indeks data terakhir.
  5. Setelah langkah ke-4 dilakukan, maka data yang berada di posisi paling kanan (indeks ke-N) adalah data terbesar .
  6. Ulangi lagi langkah 1-4 dimulai dari indeks data ke 0 sampai dengan indeks ke N-1, N-2, ..., 0


code

        def bubbleSort(listData):
            print('Data yang akan diurutkan : ', listData)
            count=0
            for outIter in range(len(listData)-1,-1,-1):
                count=count+1
                print ('Iterasi ke-', count,':')
                for i in range(outIter):
                    if listData[i]>listData[i+1]:
                        temp=listData[i]
                        listData[i]=listData[i+1]
                        listData[i+1]=temp
                        #listData[i],listData[i+1]=listData[i+1],listData[i]
                    print(listData)
            print('Data urut-',listData)
            
          a=[12,0,5,1,11,20,4,2]
          bubbleSort(a)
          b=[12,11,5,1,0]
          print('--')
          bubbleSort(b)
          

Selection Sort
adalah algoritma pengurutan yang sederhana namun sangat efisien dalam penggunaanya.

Berikut tahapan algoritma selection sort (ascending order):
  1. Algoritma ini dimulai dari indeks awal sampai dengan indeks akhir data
  2. Cari data dengan nilai paling minimal (dari indeks awal sampai dengan indeks akhir) melalui proses perbandingan
  3. Letakkan data minimal ini di indeks awal
  4. Ulangi lagi proses pencarian data paling minimal (dari indeks awal+1 sampai dengan indeks akhir, karena indeks awal sudah terisi data yang tepat).
  5. Letakkan data ini pada indeks awal+1
  6. Ulangi lagi proses pencarian data paling minimal (dari indeks awal+2 sampai dengan akhir) dan letakkan data ini pada indeks awal+2, dst.
  
  
contoh kode

    def selectionSort(listData):
        print('Algoritma Selection Sort konvensional')
        print('Data Awal=',listData)
        for outIter in range(len(listData)-1):       
            minIndex=outIter
            for i in range(outIter+1,len(listData)):
                if listData[i]<listData[minIndex]:
                    minIndex=i

            temp=listData[outIter]
            listData[outIter]=listData[minIndex]
            listData[minIndex]=temp
            print('Iterasi ke-',outIter+1,':',listData)
        print('Data Urut=',listData)
        
    a=[10,2,5,8,1,20,7,12,4]
    selectionSort(a)
    

Insertion Sort
sebuah algoritma pengurutan yang membandingkan dua elemen data pertama, mengurutkannya, kemudian mengecek elemen data berikutnya
satu persatu dan membandingkannya dengan elemen data yang telah diurutkan.

Berikut algoritma Insertion Sort :
  1. Asumsi bahwa data ke-1 sampai dengan (n/2) sudah dalam keadaan terurut
  2. Sisipkan data ke (n/2)+1 atau key ke dalam bagian data yang sudah dalam keadaan terurut, dengan cara:
      a. lakukan perbandingan data antara key dengan data pada indeks sebelumnya, jika key bernilai lebih kecil,
         maka lakukan pergeseran posisi data.
      b. lakukan terus perbandingan data key ini dengan data pada indeks sebelumnya, sampai data key tidak lebih kecil lagi
         atau sampai dengan data pada posisi pertama.

kode

      def insertionSort(listData):
          for outIter in range(1,len(listData)):
              print(listData)
              key=listData[outIter]
              ind=outIter
              while (ind>0 and listData[ind-1]>key):
                  listData[ind]=listData[ind-1]
                  ind=ind-1
                  print('inner=',listData)
              listData[ind]=key

          print('sortedData=',listData)    
          
    b=[10,2,5,8,1,20,2,2,4]
    insertionSort(b)
