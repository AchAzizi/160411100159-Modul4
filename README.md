# Rangkuman-Modul4

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



Soal Praktikum
1. Buatlah class LinkedList, dengan beberapa method tambahan pada class LinkedList seperti berikut (untuk constructor LinkedList,
   dan class Node dapat dilihat pada materi perkuliahan, serta method __str__ sama seperti praktikum sebelumnya):
      a. insertPrevious : yang digunakan untuk menyisipkan sebuah node sebelum node tertentu
      b. insertNext : yang digunakan untuk menyisipkan sebuah node sesudah nodetertentu
   Berikut adalah contoh penggunaan kedua method tersebut.
   Perintah insertNext(84,100) adalah menyisipkan node dengan data=100, sesudah node dengan data = 84.
   Sedangkan perintah insertPrevious (5,33) adalah menyisipkan node dengan data 33 sebelum node dengan data = 5
 
        mylist1=LingkedList()
        mylist1.addRear(5)
        mylist1.addRear(84)
        mylist1.addRear(12)
        mylist1.addRear(77)
        print(mylist1)
[5,84,12,77]

        mylist1.insertNext(84,100)
        print(mylist1)
[5,84,100,12,77]

        mylist1.insertPrevious(5,33)
        print(mylist)
[33,5,84,100,12,77]


2. Buatlah class Sorting, dengan property/state adalah data yang akan diurutkan (berbentuk list), dengan beberapa method berikut ini :
    a. Constructor : untuk inisialisasi property/state dari object
    b. bubbleSort, selectionSort, dan insertionSort :
        sorting dengan menggunakan algoritma bubble sort, atau selection sort, atau insertion sort, dimana terdapat parameter berupa
        jenis sorting, yaitu ‘a’ berarti hasil sorting adalah ascending, sedangkan ‘d’ berarti hasil sorting adalah descending.
        Data yang sudah diurutkan disimpan dalam property/state object tersebut. Return value, berupa waktu komputasi yang dibutuhkan
        untuk eksekusi algoritma ini.
        
   Petunjuk :
    - data yang akan diurutkan adalah data yang degenerate secara random, gunakan modul random
    - untuk menghitung waktu eksekusi, gunakan modul time, dan syntax time.time()
    
    
    
Jawaban Praktikum:

LingkedList

    class Node:
        def __init__(self, init_data):
            self.data = init_data
            self.next = None
        def getData(self): 
            return self.data
        def getNext(self): 
            return self.next
        def setData(self, newdata):
            self.data = newdata
        def setNext(self, new_next):
            self.next = new_next
    class LinkedList:
        def __init__(self):
            self.head=None
        def isEmpty(self):
            return self.head==None
        def size(self):
            current = self.head
            count = 0
            while current != None:
                count+=1
                current=current.getNext()
            return count
        def addRear(self,item):
            temp=Node(item)
            if self.isEmpty()==True:
                self.head=temp
            else:
                current=self.head
                previous=None
                while current != None:
                    previous=current
                    current=current.getNext()
                previous.setNext(temp)
        def __str__(self):
            data="["
            current=self.head
            while current!=None:
                data+=str(current.data)
                current=current.getNext()
                if current!=None:
                    data+=","
            data+="]"
            return(data)
        def insertPrevious(self,obj,item):
            temp=Node(item)
            current=self.head
            previous=None
            stop=False
            while current!=None and not stop:
                if current.getData()==obj:
                    stop=True
                else:
                    previous=current
                    current=current.getNext()
            if stop==True:
                temp.setNext(current)
                previous.setNext(temp)
        def insertNext(self,obj,item):
            temp=Node(item)
            current=self.head
            previous=current
            stop=False
            while current!=None and not stop:
                if previous.getData()==obj:
                    stop=True
                else:
                    previous=current
                    current=current.getNext()
            if stop==True:
                temp.setNext(current)
                previous.setNext(temp)

    myList1=LinkedList()
    myList1.addRear(5)
    myList1.addRear(84)
    myList1.addRear(12)
    myList1.addRear(77)
    print (myList1)
    ##myList1.insertPrevious(84,100)
    myList1.insertNext(84,100)
    print("Insert: ",myList1)
    ##myList1.insertNext(12,122)
    myList1.insertPrevious(5,33)
    print("Insert: ",myList1)
    

Bubble Sort

    import time
    import random
    class Sorting:
        def __init__(self,a):
            self.Data=a
        def bubbleSort(self,pilihan):
            t1=time.time()/10000000000
            #print('Data yang akan diurutkan : ', self.Data)
            if pilihan=="a": #data urutan naik
                for outIter in range(len(self.Data)-1,-1,-1):
                    for i in range(outIter):
                        if self.Data[i]>self.Data[i+1]:
                            self.Data[i],self.Data[i+1]=self.Data[i+1],self.Data[i]
            elif pilihan=="d": #data urutan turun
                for outIter in range(len(self.Data)-1,-1,-1):
                    for i in range(outIter):
                        if self.Data[i]<self.Data[i+1]:
                            self.Data[i],self.Data[i+1]=self.Data[i+1],self.Data[i]
            return t1
        def selectionSort(self,pilihan):
            t1=time.time()/10000000000
            for outIter in range(len(self.Data)-1):       
                minIndex=outIter
                if pilihan=="a":
                    for i in range(outIter+1,len(self.Data)):
                        if self.Data[i]<self.Data[minIndex]:
                            minIndex=i
                    self.Data[outIter],self.Data[minIndex]=self.Data[minIndex],self.Data[outIter]
                if pilihan=="d":
                    for i in range(outIter+1,len(self.Data)):
                        if self.Data[i]>self.Data[minIndex]:
                            minIndex=i
                    self.Data[outIter],self.Data[minIndex]=self.Data[minIndex],self.Data[outIter]
            return t1
        def insertionSort(self,pilihan):
            t1=time.time()/10000000000
            for outIter in range(1,len(self.Data)):
                key=self.Data[outIter]
                ind=outIter
                if pilihan=="a":
                    while (ind>0 and self.Data[ind-1]>key):
                        self.Data[ind]=self.Data[ind-1]
                        ind=ind-1
                    self.Data[ind]=key
                if pilihan=="d":
                    while (ind>0 and self.Data[ind-1]<key):
                        self.Data[ind]=self.Data[ind-1]
                        ind=ind-1
                    self.Data[ind]=key
            return t1

    t1=time.time()
    ##a=random.sample(range(0, 1000),500)
    ##dataSort=Sorting(a)
    ##t1=dataSort.bubbleSort("a")
    ##print(dataSort.Data)
    ##print('waktu komputasi',t1,'detik')
