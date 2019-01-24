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
```sh
https:heksainsurance.co.id/posmgmapi/api/submitsuccessdata
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
|WORDS| | [text] | Y |254 | enkripsi kombinasi Premium+MerchantID+Sharedkey SharedKey diberikan oleh heksa insurance|
|ProductName| | [text] | Y |150 | Nama Produk Asuransi|
|ProductPackageName| |[text] | Y |150 | Nama Paket (Lihat List)|
|ProductType| |[number] | Y |  | 1 = Bulanan, 2 = Tahunan |
|Premium| |[number]| Y | | |
|SumInsured| |[number]| Y | | |
|ReferenceCode| |[text] | Y | 20 | Kode pemberi referral |
|TransactionCode| |[text] | Y | 20 | digenerate oleh Pos Indonesia |
|TransactionDate| |[date] | Y | | format dd/MM/yyyy |
|InsuredRelation| |[text] | Y | 100 | Hubungan Pemegang Polis dengan Tertanggung (Lihat List) |
|PaymentStatus| |[text] | Y | 10 | 200 = Berhasil, 500 = Gagal |
|PolicyHolder| |[jsonObject] | Y | | Pemegang Polis |
|| FullName |[text] | Y | 250 | |
|| Sex |[text] | Y | | pria, wanita |
|| Email |[text] | Y | 50 | |
|| Phone |[text] | Y | 15 | |
|| KTPNo |[text] | Y | 20 | |
|| NPWP |[text] | Y | 20 | |
|| BirthPlace |[text] | Y |150| Tempat tanggal lahir|
|| DOB |[date] | Y | | Tanggal Lahir format dd/MM/yyyy|
|| Address |[text] | Y | 500 | Alamat Sesuai Identitas |
|| ProvinceName |[text] | Y | 100 | Provinsi Sesuai Identitas  |
|| CityName |[text] | Y | 100 | Kota Sesuai Identitas |
|| SourcesOfFinance |[text] | Y | 100 | Sumber Dana (Lihat List) |
|| MonthlyIncome |[text] | Y | 100 | Penghasilan Perbulan (Lihat List) |
|| FiledOfWork |[text] | Y | 100 | Bidang Pekerjaan (Lihat List) |
|| Height |[number]| Y | | Tinggi Badan |
|| Weight |[number]| Y | | Berat Badan |
|Insured| |[jsonObject] | Y | | Tertanggung |
|| FullName |[text] | Y | 250 | |
|| Sex |[text] | Y | | pria, wanita |
|| Email |[text] | Y | 50 | |
|| Phone |[text] | Y | 15 | |
|| KTPNo |[text] | Y | 20 | |
|| NPWP |[text] | Y | 20 | |
|| BirthPlace |[text] | Y |150| Tempat tanggal lahir|
|| DOB |[date] | Y | | Tanggal Lahir format dd/MM/yyyy|
|| Address |[text] | Y | 500 | Alamat Sesuai Identitas |
|| ProvinceName |[text] | Y | 100 | Provinsi Sesuai Identitas  |
|| CityName |[text] | Y | 100 | Kota Sesuai Identitas |
|| SourcesOfFinance |[text] | Y | 100 | Sumber Dana |
|| MonthlyIncome |[text] | Y | 100 | Penghasilan Perbulan |
|| FiledOfWork |[text] | Y | 100 | Bidang Pekerjaan |
|| Height |[number]| Y | | Tinggi Badan |
|| Weight |[number]| Y | | Berat Badan |
|Beneficiary| |[jsonObject] | Y | | Ahli Waris |
|| FullName |[text] | Y | 50 | |
|| Sex |[text] | Y | | pria, wanita |
|| DOB |[date] | Y | | format dd/MM/yyyy|
|| Relation |[text] | Y | | Hubungan Ahliwaris dengan Tertanggung (Lihat List)|
|Bank| |[jsonObject] | Y | | Data Bank |
|| BankName |[text] | Y | |  Nama Bank|
|| BankBranch |[text] | Y | | Cabang Bank |
|| BankAccountName |[text] | Y | | Nama Pemilik Rekening |
|| BankAccountNo |[text] | Y | | Nomer Rekening |
#

##### - Result Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| StatusCode |  | [Text] | Y | 4 | 200 = Berhasil, 500 = Gagal |
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
