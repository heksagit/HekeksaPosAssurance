# API Gateway Heksa Insurance x Pos Assurance
PT Asuransi Heksa Insurance X PT Pos Indonesia 
___________________________________________________________


### Submit aplication Data
#### URL & Params Required:
##### - Features
  - Sender : **PT POS INDONESIA**
  - Target API : **Heksa Insurance**
  - Submit Data aplication from **POS Indonesia** to **Heksa Insurance** API
#

##### - Endpoint
  - **PRODUCTION**
```sh
https:heksainsurance.co.id/heksaapi/api/submitsuccessdata
```
  - **DEVELOPMENT**
```sh
http://103.58.146.64/heksaapi/api/submitsuccessdata
```
#

##### - Method : POST
#

##### - Authorization Basic Auth

| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y |150 |Username untuk basic auth - diberi oleh heksa insurance |
|password|[text] | Y |150 |Password basic auth - diberi oleh heksa insurance |

#
##### - Body Structure

| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|MerchantID| | [text] | Y |50 | ID Merchant diberikan oleh Heksa Insurance|
|SessionID| | [text] | Y |50 | Digenerate Oleh POS Indonesia harus Uniq untuk setiap request|
|WORDS| | [text] | Y |254 | enkripsi kombinasi SessionID+Premium+MerchantID+Sharedkey SharedKey diberikan oleh heksa insurance|
|ProductCode| | [text] | Y |150 | Kode Produk Asuransi|
|Premium| |[decimal]| Y | | |
|IsPrintPolicy| |[number]| Y | | 1 = Jika Polis ingin dicetak, 0 = Jika Polis tidak ingin dicetak |
|PolicyPrintingCost| |[decimal]| Y | | Biaya Cetak Polis |
|TransactionDate| |[text] | Y | | format dd/MM/yyyy |
|InsuredRelation| |[text] | Y | 100 | Hubungan Pemegang Polis dengan Tertanggung (Lihat List) |
|AplicationType| |[text] | Y | 5 | Tipe Pembelian : 1 = Agen Sendiri, 2 = Orang Lain |
|AgenCode| |[text] | Y | 5 | Di isi Kode Agen yang punya Account |
|PolicyHolder| |[jsonObject] | Y | | Pemegang Polis |
|| FullName |[text] | Y | 250 | |
|| Sex |[text] | Y | | P/W |
|| Email |[text] | Y | 50 | |
|| Phone |[text] | Y | 15 | |
|| KTPNo |[text] | Y | 20 | |
|| NPWP |[text] | N | 20 | |
|| BirthPlace |[text] | Y |150| Tempat tanggal lahir|
|| DOB |[date] | Y | | Tanggal Lahir format dd/MM/yyyy|
|| Address |[text] | Y | 500 | Alamat Sesuai Identitas |
|| ProvinceName |[text] | Y | 100 | Provinsi Sesuai Identitas  |
|| CityName |[text] | Y | 100 | Kota Sesuai Identitas |
|| District |[text] | Y | 100 | Kecamatan Sesuai Identitas |
|| SourcesOfFinance |[text] | Y | 100 | Sumber Dana (Lihat List) |
|| MonthlyIncome |[text] | Y | 100 | Penghasilan Perbulan (Lihat List) |
|| FiledOfWork |[text] | Y | 100 | Bidang Pekerjaan (Lihat List) |
|| CorrespondenceAddress |[text] | Y | 500 | Alamat Pengiriman Polis |
|| CorrespondenceProvinceName |[text] | Y | 100 | Provinsi Pengiriman Polis  |
|| CorrespondenceCityName |[text] | Y | 100 | Kota Pengiriman Polis |
|| CorrespondenceDistrict |[text] | Y | 100 | Kecamatan Pengiriman Polis |
|Insured| |[jsonObject] | Y | | Tertanggung |
|| FullName |[text] | Y | 250 | |
|| Sex |[text] | Y | | P/W |
|| Email |[text] | Y | 50 | |
|| Phone |[text] | Y | 15 | |
|| KTPNo |[text] | Y | 20 | |
|| NPWP |[text] | N | 20 | |
|| BirthPlace |[text] | Y |150| Tempat tanggal lahir|
|| DOB |[text] | Y | | Tanggal Lahir format dd/MM/yyyy|
|| Address |[text] | Y | 500 | Alamat Sesuai Identitas |
|| ProvinceName |[text] | Y | 100 | Provinsi Sesuai Identitas  |
|| CityName |[text] | Y | 100 | Kota Sesuai Identitas |
|| District |[text] | Y | 100 | Kecamatan Sesuai Identitas |
|| Height |[number]| Y | | Tinggi Badan |
|| Weight |[number]| Y | | Berat Badan |
|Beneficiary| |[jsonObject] | Y | | Ahli Waris |
|| FullName |[text] | Y | 50 | |
|| Sex |[text] | Y | | P/W |
|| DOB |[text] | Y | | format dd/MM/yyyy|
|| Relation |[text] | Y | | Hubungan Ahliwaris dengan Tertanggung (Lihat List)|
|Referral| |[jsonObject] | Y | | Data Pemberi Referral |
|| Name |[text] | N | |  Nama Pemberi Referral|
|| Code |[text] | Y | | Code Referral di isi Kode Agen pemberi referral |
|| Email |[text] | N | | Email Referral |
|| Phone |[text] | N | | Nomor Handphone Referral |
#

##### - Result Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| StatusCode |  | [Text] | Y | 4 | "00" = Berhasil, "500" = Gagal |
| StatusMessage |  | [Text] | Y | 100 |  |
| Value |  | [Text] | Y | 1500 | string object json |
#

###### Failed Response
```sh
{
    "StatusCode": "500",
    "StatusMessage": "There is an error in system",
    "Value" : null
}
```
#
____________________________________________________________________

#### Pernyataan Pekerjaan
Pernyataan dibawah ini merupakan pernyataan kamu/calon tertanggung mengenai persyaratan produk Heksa DOA Dompet Asuransi
___________________________________________________________
- Saya/Calon Tertanggung bukanlah Anggota Pasukan Khusus/Elite TNI/POLRI
- Saya/Calon Tertanggung bukanlah Pilot, Pramugari atau Mahasiswa Penerbangan
- Saya/Calon Tertanggung bukanlah pekerja lapangan di Pertambangan, Minyak Bumi dan Gas Alam
- Saya/Calon Tertanggung bukanlah Mekanik Listrik Tegangan Tinggi
- Saya/Calon Tertanggung bukanlah Pembersih kaca jendela ketinggian diatas 50 kaki
- Saya/Calon Tertanggung bukanlah Pekerja yang terpapar zat beracun, radiasi nuklir 
- Saya/Calon Tertanggung bukanlah Pekerja Pelayaran/Pelaut, Nelayan
- [x] Saya setuju dengan kondisi pernyataan di atas
____________________________________________________________________

#### Pernyataan Kesehatan
Pernyataan dibawah ini merupakan pernyataan kamu/calon tertanggung mengenai persyaratan produk Heksa DOA Dompet Asuransi
___________________________________________________________
- Saya/Calon Tertanggung sehat, tidak sedang dirawat di Rumah Sakit
- Saya/Calon Tertanggung tidak  pernah atau sedang menderita salah satu dari penyakit, gejala penyakit / kelainan yang berhubungan dengan : cacat / kelumpuhan, tumor / kanker / kista, TBC atau penyakit paru lainnya, asma, Diabetes, penyakti Hati, penyakit Ginjal, penyakit Jantung, penyakit Jantung bawaan, Stroke / mini stroke, Hipertensi, gangguan jiwa, pencangkokan organ tubuh, HIV / AIDS, penyakit kritis bawaan sejak lahir / kongenital, penyakit darah dan pembuluh darah, penyakit Autoimune dan Kolesterolemia.
- Saya/Calon Tertanggung dalam 2 tahun terakhir tidak pernah didiagnosis dengan penyakit, gangguan atau cedera yang membutuhkan konsultasi yang berkelanjutan, rawat inap atau perawatan medis secara terus menerus selama 7 hari atau lebih (kecuali untuk flu, infeksi saluran pernafasan atau penyakit virus) atau pernah menjalani pembedahan atau menjalani tes medis dengan hasil tidak normal (misalnya : tes darah atau urin, USG, CT scan, MRI, biopsi dll).
- Saya/Calon Tertanggung tidak sedang hamil 
- [x] Saya setuju dengan kondisi pernyataan di atas
____________________________________________________________________

#### Statment Nasabah
___________________________________________________________
- [x] Saya menyatakan bahwa keterangan kesehatan di atas adalah yang sebenarnya dan merupakan bagian yang tidak terpisahkan dari proses permintaan asuransi yang saya ajukan. Apabila pernyataan yang saya berikan tersebut tidak benar, maka PT. Heksa Solution Insurance berhak membatalkan asuransi dan berhak tidak membayar klaim yang dibuat atas dasar permohonan ini dan tidak diwajibkan mengembalikan uang premi yang telah dibayar atas nama saya. Selanjutnya saya memberi kuasa kepada setiap Dokter/Rumah Sakit/Perusahaan Asuransi/Badan Hukum/Perorangan atau Organisasi lainnya, yang mempunyai catatan atau mengetahui keadaan atau kesehatan saya untuk memberitahukan kepada PT. Heksa Solution Insurance atau mereka yang diberi kuasa olehnya, segala keterangan tentang diri dan kesehatan baik semasa saya masih hidup maupun sesudah saya meninggal dunia.
- [x] Saya menyatakan bahwa Penerima Manfaat yang terlampir pada eSPAJ (Surat Permohonan Asuransi Jiwa Digital) telah memenuhi sebagai pihak yang memiliki kepentingan yang dapat diasuransikan (Insurable Interest) dan memiliki bukti yang sah secara hukum untuk membuktikan hubungannya dengan Tertanggung. Apabila ada data dan informasi yang berbeda, dengan ini saya membebaskan PT Heksa Solution Insurance dari segala tuntutan dari pihak manapun.
- [x] Saya menyatakan bahwa semua Pernyataan atau Keterangan yang saya sampaikan telah lengkap, benar dan sesuai. Apabila terdapat Pernyataan atau Keterangan yang tidak sesuai dengan kondisi sebenarnya, baik disengaja maupun tidak, maka PT Heksa Solution Insurance berhak membatalkan polis dan atau tidak berkewajiban untuk menyetujui permohonan asuransi ini.
                                                                
___________________________________________________________

