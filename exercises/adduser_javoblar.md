# 📝 Mashqlar javoblari: adduser
## 🟢 Easy
1. `adduser` buyrug‘i nima vazifa bajaradi?

`adduser` — Linux tizimida yangi foydalanuvchi (user) yaratish uchun ishlatiladi.
U atomatik tarzda:
- user yaratadi
- home directory ochadi
- parol o‘rnatadi

2. Yangi user yaratish uchun qanday buyruq ishlatiladi?

`sudo adduser username`

Misol:

`sudo adduser ali`

3. `sudo` nima uchun kerak?

`sudo` — buyruqni administrator (root) huquqlari bilan bajarish uchun kerak.

👉 Oddiy user:

yangi user yarata olmaydi
tizimga o‘zgartirish kirita olmaydi

## 🟡 Medium
1. `testuser` nomli foydalanuvchi yarating 

`sudo adduser testuser`

2. Yaratilgan userning `home directory` qayerda joylashadi?

`/home/testuser`

👉 Har bir user uchun alohida katalog yaratiladi.

3. Yangi user yaratishda qanday ma’lumotlar so‘raladi?

`adduser` quyidagilarni so‘raydi:

- Parol
- Full name (ixtiyoriy)
- Room number (ixtiyoriy)
- Phone (ixtiyoriy)

👉 Asosiysi: parol

## 🔴 Hard
1. Yangi user yarating va uni sudo groupga qo‘shing
- 1-qadam: user yaratish

`sudo adduser ali`

- 2-qadam: sudo groupga qo‘shish

`sudo usermod -aG sudo ali`

👉 Tekshirish:

`groups ali`

👉 Natija:

`ali : ali sudo`

2. Nima uchun har bir `user` uchun alohida `home` directory kerak?

Bu juda muhim tushuncha 👇

- 🔹 1. Xavfsizlik
Har bir user o‘z fayllariga egalik qiladi
Boshqa userlar kira olmaydi (ruxsatsiz)
- 🔹 2. Izolyatsiya
Bir user boshqasiga xalaqit bermaydi
Konfiguratsiyalar alohida saqlanadi
- 🔹 3. Shaxsiy muhit
.bashrc, .config kabi fayllar

Har user o‘z sozlamasiga ega

👉 Xulosa:
Home directory — bu userning shaxsiy ish muhiti

3. `adduser` va `useradd` o‘rtasidagi farq

Bu juda muhim savol 🔥

| Xususiyat | adduser |	useradd |
| --------- | ------- | ------- |
| Daraja	| High-level	| Low-level |
| Interaktiv |	Ha	| Yo‘q |
| Osonlik	| Oson	| Murakkab |
| Avtomatika	| Ko‘p	| Kam |

- 🔹 adduser
    * Foydalanuvchi uchun qulay
    * Savollar beradi
    * Home directory avtomatik yaratadi
    * `sudo adduser ali`

- 🔹 useradd
    * Past darajadagi buyruq
    * Qo‘lda sozlash kerak
    * `sudo useradd ali`

👉 Home directory yaratish uchun:

`sudo useradd -m ali`

👉 Parol berish:

`sudo passwd ali`

🔥 Xulosa:

adduser → boshlovchilar uchun
useradd → admin va advanced userlar uchun

🧠 Bonus savollar
1. Agar noto‘g‘ri user yaratilsa, uni qanday o‘chirish mumkin?

`sudo deluser username`

👉 Home directory bilan:

`sudo deluser --remove-home username`

2. Linux’da userlar qayerda saqlanadi?

`/etc/passwd`

👉 Qo‘shimcha:

`/etc/shadow` → parollar (encrypted)
`/etc/group` → group ma’lumotlari

🚀 Yakuniy xulosa

Agar shu savollarni tushunsang:

✅ user yaratish
✅ user boshqarish
✅ system ichki tuzilmasi