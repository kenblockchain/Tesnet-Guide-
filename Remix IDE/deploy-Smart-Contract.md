[Buka Remix Ethereum](https://remix.ethereum.org/#optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.7+commit.e28d00a7.js)


Lalu pada tampilan awal pilih Solidity



![Cuplikan web_25-9-2022_92230_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664072560454/Vh3LO2rGv.jpeg align="left")


Setelah itu buatlah file baru


![Cuplikan web_25-9-2022_92334_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664072625935/C9VHJW_CC.jpeg align="left")



Disini saya menggunakan nama condor.sol


![Cuplikan web_25-9-2022_92452_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664072710755/ySMLTEBnH.jpeg align="left")



> Lanjut ke Github ,disana sudah ada code yang bisa digunakan

[https://gist.github.com/alinustorvalt/af2188cc661db97ce561aa4301e8456f](https://gist.github.com/alinustorvalt/af2188cc661db97ce561aa4301e8456f)

> Ubah semua yang ditandai dengan apapun yang kamu mau, isi minter dengan address dari wallet mu . Symbol ,nama token,total supply bisa diubah sesuka hati


> Bisa juga menggunakan source code yang lebih simple (konsep mengerjakannya sama)


[https://gist.github.com/alinustorvalt/c076523f156bacc363a511966566fb51](https://gist.github.com/alinustorvalt/c076523f156bacc363a511966566fb51)


![Cuplikan web_25-9-2022_94936_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664074300733/HHrTa2uVU.jpeg align="left")

Setelah disesuaikan, paste semua code tadi ke dalam file .sol yang kita buat di awal



![Cuplikan web_25-9-2022_102240_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664076216787/pKU3NqE7D.jpeg align="left")


> Lalu pergi ke menu Solidity Compiler

> Karena didalam code kita menggunakan Solidity versi 0.8.2


![Cuplikan web_25-9-2022_9544_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664074453948/Av64Xfo7U.jpeg align="left")

> Maka kita ubah Compiler nya sesuai dengan versi yang sama 
v0.8.2+commit.661d1103



![Cuplikan web_25-9-2022_9552_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664074519997/N6-U02d7e.jpeg align="left")



> Selanjutnya kita Compile


![Cuplikan web_25-9-2022_9561_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664074574442/puIABQnjT.jpeg align="left")


> Jika sudah muncul seperti ini , berarti file itu telah ter-compile


![Cuplikan web_25-9-2022_95652_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664074633525/nSLKcUuWX.jpeg align="left")


Selanjutnya pergi ke menu  **Deploy & Run Transactions**


![Cuplikan web_25-9-2022_95815_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664074705690/mxNgDNvVK.jpeg align="left")


Ganti Environment ke ***Injected Provider - Metamask***


![Cuplikan web_25-9-2022_95928_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664074783333/3aZtIok5n.jpeg align="left")


Pastikan Jaringan Condor Testnet sudah ditambahkan ke Metamask mu



![Cuplikan web_25-9-2022_10010_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664074821083/XcaRY5YWU.jpeg align="left")


• RPC URL: http://66.42.86.39:8545

• CHAIN ID: 188881

• COIN NAME: CONDOR

• BLOCK EXPLORER: http://96.30.194.234:4000/



![Cuplikan web_25-9-2022_10120_nkbihfbeogaeaoehlefnkodbefgpgknn.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075006451/TQb13whvo.jpeg align="left")


> Selanjutnya, pada bagian Contract ubah ***IcyTail - contract/condor.sol***
menjadi  ***contract/condor.sol***



![Cuplikan web_25-9-2022_1056_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075117083/BFt4L9zIU.jpeg align="left")


*Kenapa kenblockchain? karena itu nama token yang kubuat , silahkan sesuaikan dengan nama token mu sendiri*



![Cuplikan web_25-9-2022_10550_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075165937/UmLRZEo4m.jpeg align="left")


Lalu klik Deploy dan Approve transaksi itu di Metamask




![Cuplikan web_25-9-2022_10715_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075249096/5_ScgX9ft.jpeg align="left")


Jika sudah akan ada banyak fungsi dari Smart Contract yang kita buat tadi


![Cuplikan web_25-9-2022_10810_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075302577/1YZKwmmjc.jpeg align="left")


## Selanjutnya adalah langkah untuk memverifikasi Smart Contract


> Copas semua Code dari Smart Contract tadi



![Cuplikan web_25-9-2022_10956_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075412688/7xEB4iCp6.jpeg align="left")


> Lalu pergi [Explorer ](http://96.30.194.234:4000/tx/0xd3fd01b22213d0b2f237a9e49ef12f6c7733f95ffc3b1c98ab5d31072249ec3d), cek riwayat transaksi saat membuat Smart Contract
> Lihat detail Smart Contract tersebut


![Cuplikan web_25-9-2022_10114_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075473204/Z-qp4JVkY.jpeg align="left")


> Pilih menu Code


![Cuplikan web_25-9-2022_101236_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075564190/BrlrVt0KS.jpeg align="left")


> Klik Verify & Publish



![Cuplikan web_25-9-2022_101321_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075613181/jnFGSk_WO.jpeg align="left")


> Next


![Cuplikan web_25-9-2022_101359_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075648155/ebp0OLHYQ.jpeg align="left")

> *Pada bagian Contract Name ,isi dengan nama yang ada di code tadi*


![Cuplikan web_25-9-2022_101441_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075692790/BBGGCKmOe.jpeg align="left")


> *Di Compiler pilih v0.8.2+commit.661d1103*


![Cuplikan web_25-9-2022_101817_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075915751/_GwwUneeu.jpeg align="left")


> Paste semua isi file .sol ke Enter the Solidity Contract Code



![Cuplikan web_25-9-2022_101857_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664075950710/N0gdNhkQB.jpeg align="left")


> Try to fetch bla bla bla pilih Yes atau No bebas dan ABI-encoded bla bla bla tidak usah diisi



![Cuplikan web_25-9-2022_101952_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664076004260/KxzbwVDF4.jpeg align="left")


> Terakhir Verify & Publish ,dan tunggu sampai selesai


![Cuplikan web_25-9-2022_102046_mirror.xyz.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664076054525/r3VC_hx4M.jpeg align="left")


