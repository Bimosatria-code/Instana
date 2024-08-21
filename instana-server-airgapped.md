# Install Instana Server Airgapped

1. Download instana-server dengan menjalankan “**[https://_](https://_/):(download-key)@packages.instana.io/airgapped/” dibrowser**
2. Kemudian setelah didownload copy file ke dalam server
3. Sebelum kita mengextract kita buat directory dengan command “**sudo mkdir /mnt/{data,metrics,traces}**”
4. Setelah itu Extract file didalam server dan masuk kedirectory docker-installer
5. Setelah itu jalankan “**./instana images import -f ../images/containers.tar” untuk mengimport images**
6. Setelah itu jalankan “**./instana init -f ./settings.hcl**” untuk menginstall instana server
7. Setelah selesai proses instalasi copas url, user dan password
8. Kemudian copy masuk license yg sudah dimiliki kedalam server
9. Lalu setelah itu jalankan “**./instana license import -f ./license**”
10. Jika import sudah selesai jalankan “**./instana license verify**” untuk memverifikasi
11. Tambahkan Config EUM pada file setting.hcl untuk mengaktifkan tracking pada mobile 

**eum {
tracking_base_url     = "https://mobile.acmecorp.com/eum/"
}**
