# Excels

Formulas in Jurnal-Jual

Sheets:
PL: Summary of Stok_In and Penjualan/Rangkuman dari Stok_In dan Penjualan
Stok_In: Sheet for input product's stock/purchases in warehouse/Halaman untuk memasukkan stok produk/pembelian produk di gudang 
Penjualan: Sheet for input product's sales in warehouse/Halaman untuk memasukkan penjualan produk di gudang 
Jurnal_Kas: Sheet for input cashflow/Halaman untuk memasukkan arus kas

PL:
Example:
![image](https://github.com/Maizi12/Excels/assets/66654676/d1d6d1d9-2f31-4e26-b2bc-9583b0beed8d)

So in this sheet, there are some columns like 'Nama_Barang' or 'Product_Name', 'Harga Modal' or 'Purchase_price', 'Stok Masuk' or 'Goods In', 'Terjual' or 'Sold', 'Rusak' or 'defective goods', 'Sisa Stok' or 'Remaining goods', 'Awal-1' or 'initial goods-1 price', 'Masuk-1' or 'Goods In-1 price', 'Terjual-1' or 'Sold-1', and 'Sisa-1' or 'Remaining-1'
Jadi di halaman ini, ada beberapa kolom seperti Nama Barang, Harga Modal, Stok Masuk, Terjual, Rusak, Sisa Stok, Awal-1, Masuk-1, Terjual-1, Sisa-1.

Nama_Barang or Product_Name is a column to fill in the product name, obviously. This column is required for other columns since this column is one of the main parameters
Nama_Barang atau Product_Name adalah kolom untuk mengisi nama produk, jelas. Kolom ini diperlukan untuk kolom-kolom lain karena kolom ini adalah salah satu parameter utama.

Harga Modal or Purchase_Price is a column to fill in the product's purchase price. You can use the included formula, or manually input it. But for concistency, I'd use the formula: AVERAGEIF(Stok_In[Nama Barang];[@[NAMA_BARANG]];Stok_In[Harga]). This resulted in the average price based on the product name.
Harga Modal adalah kolom untuk mengisi harga pembelian barang. Anda bisa menggunakan formula yang disertakan atau memasukkannya secara manual. Tapi untuk konsistensi, saya menggunakan formula: AVERAGEIF(Stok_In[Nama Barang];[@[NAMA_BARANG]];Stok_In[Harga]). Ini menghasilkan harga rata-rata berdasarkan nama produk.

Stok_Masuk or Goods In is a column to fill in the purchased goods and goods from last period. The Formula:=SUMIFS(Stok_In[Qty];Stok_In[Status];"Masuk";Stok_In[Nama Barang];[@[NAMA_BARANG]])+SUMIFS(Stok_In[Qty];Stok_In[Status];"Awal";Stok_In[Nama Barang];[@[NAMA_BARANG]]). This formula basically sums Quantity of purchased goods and goods from last period. The parameter is the product's name and the status in the Stok_In which only takes two types of status, "Masuk" and "Awal". "Masuk" is for purchased goods, and "Awal" is for goods from last period. You can adjust this for yourself.
