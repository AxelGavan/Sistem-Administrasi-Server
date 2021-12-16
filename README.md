# **Laporan modul 3**

## **Axel Gavan & Charisma Ilham Saputra**

### **Problem Solving**

* Masuk ke direktori menggunakan ansible

  <p align="center">
        	<img src= "https://github.com/acid99/Sistem-Administrasi-Server/blob/main/assets/laprak3/2021-12-15.png?raw=true">
  </p>
  <p align="center">
        	<img src= "https://github.com/acid99/Sistem-Administrasi-Server/blob/main/assets/laprak3/2021-12-15_1.png?raw=true">
  </p>

  ```
  ---
  - hosts: all
    become : yes
    tasks:
      - name: install bind9 dan dnsutils
        apt:
         pkg:
           - bind9
           - dnsutils
  ```

* Install sublaravel.yml dengan ansible

  <p align="center">
        	<img src= "https://github.com/acid99/Sistem-Administrasi-Server/blob/main/assets/laprak3/2021-12-15_2.png?raw=true">
  </p>


* Membuat file config.yml

  <p align="center">
        	<img src= "https://github.com/acid99/Sistem-Administrasi-Server/blob/main/assets/laprak3/2021-12-15_3.png?raw=true">
  </p>

  ```
  ---
  - hosts: all
    become : yes
    tasks:
     - name: membuat direktori
       file:
        path: /var/www/html/dev/landing
        state: directory
     - name: copy file vm.local
       copy:
        src: /etc/bind/vm/vm.local
        dest: /var/www/html/dev/landing
     - name: mengganti konfigurasi
       replace:
        path: /var/www/html/dev/landing/vm.local
        regexp: 'www'
        replace: 'dev'
     - name: copy file named.conf.local
       copy:
        src: /etc/bind/named.conf.local
        dest: /etc/bind/named.conf.local
     - name: mengganti konfigurasi conf local
       replace:
        path: /etc/bind/named.conf.local
        regexp: '/etc/bind/vm/vm.local'
        replace: '/var/www/html/dev/landing/vm.local'
     - name: mengganti konfigurasi conf local part2
       replace:
        path: /etc/bind/named.conf.local
        regexp: '/etc/bind/vm/115.168.192.in-addr.arpa'
        replace: '/var/www/html/dev/landing/115.168.192.in-addr.arpa'
     - name: copy file 115.168.192.in-addr.arpa
       copy:
        src: /etc/bind/vm/115.168.192.in-addr.arpa
        dest: /var/www/html/dev/landing
     - name: copy file resolv.conf
       copy:
        src: /etc/resolv.conf
        dest: /etc/resolv.conf
     - name: copy file named.conf.options
       copy:
        src: /etc/bind/named.conf.options
        dest: /etc/bind/named.conf.options
     - name: restart nginx
       service:
        name: nginx
        state: restarted
     - name: restart bind9
       action: service name=bind9 state=restarted
  ```

* Lakukan instalasi menggunakan perintah seperti ini

  <p align="center">
        	<img src= "https://github.com/acid99/Sistem-Administrasi-Server/blob/main/assets/laprak3/2021-12-15_4(fix).png?raw=true">
  </p>
  
* Menambahkan subdomain ke /etc/hosts

  <p align="center">
        	<img src= "https://user-images.githubusercontent.com/94977405/146429447-114e4ba5-272b-480c-b2d6-a2bc0a8c633b.png">
  </p>

* Buka file vm.local 

  <p align="center">
        	<img src= "https://github.com/acid99/Sistem-Administrasi-Server/blob/main/assets/laprak3/2021-12-15_6.png?raw=true">
  </p>

* Tambahkan baris www. kemudian keluar LXC

  <p align="center">
        	<img src= "https://user-images.githubusercontent.com/94977405/146432353-56120d40-02ce-47d6-8b3d-9131d3386dc9.png">
  </p>

* Buka dan edit vm.local pada directory /etc/nginx/sites-enabled/

  <p align="center">
        	<img src= "https://github.com/acid99/Sistem-Administrasi-Server/blob/main/assets/laprak3/2021-12-15_9.png?raw=true">
  </p>

  <p align="center">
        	<img src= "https://user-images.githubusercontent.com/94977405/146431697-c644edee-cd17-4830-9b44-a8e976862e43.png">
  </p>
  
* Buka dan edit vm.local pada directory /etc/bind/vm/

  <p align="center">
        	<img src= "https://user-images.githubusercontent.com/94977405/146430857-e5b72933-7426-4382-8cf0-73ec61c2a377.png">
  </p>

* Restart bind9 dan nginx

  <p align="center">
        	<img src= "https://github.com/acid99/Sistem-Administrasi-Server/blob/main/assets/laprak3/2021-12-16_1.png?raw=true">
  </p>

- Buka pengaturan Wifi,kemudian tambahkan server dns dan hapus tanda centang pada menu IPv4

  <p align="center">
        	<img src= "https://user-images.githubusercontent.com/94977405/146427284-4061d952-d10a-443f-bfdb-5ccb0a29dfb7.png">

- Hapus tanda centang pada menu IPv6  

  <p align="center">
        	<img src= "https://user-images.githubusercontent.com/94977405/146427319-0181466f-f1ca-4a85-80b5-1c87bb4b1ebe.png">

- Sambungkan ke wifi dan cek pada browser dev.vm.local

  <p align="center">
        <img src= "https://user-images.githubusercontent.com/94977405/146427357-0574e636-1e47-42bd-bc2a-2a49a294f6c4.png">
