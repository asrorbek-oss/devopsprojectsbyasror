## Eski versiyalarni o‘chirish

Docker Engine'ni o‘rnatishdan oldin, u bilan ziddiyatga kirishi mumkin bo‘lgan eski paketlarni o‘chirib tashlash kerak.

Linux distributivingiz Docker'ning norasmiy paketlarini taqdim etishi mumkin. Ushbu paketlar Docker tomonidan taqdim etilgan rasmiy paketlar bilan to‘qnashishi mumkin. Shuning uchun Docker Engine'ning rasmiy versiyasini o‘rnatishdan oldin ularni o‘chirib tashlash tavsiya etiladi.

O‘chirilishi kerak bo‘lgan norasmiy paketlar:

* `docker.io`
* `docker-compose`
* `docker-compose-v2`
* `docker-doc`
* `podman-docker`

Bundan tashqari, Docker Engine ishlashi uchun `containerd` va `runc` komponentlariga tayanadi. Docker Engine ushbu bog‘liqliklarni `containerd.io` paketi tarkibida birga olib keladi.

Agar siz avval `containerd` yoki `runc` paketlarini alohida o‘rnatgan bo‘lsangiz, Docker bilan versiya ziddiyatlari yuzaga kelmasligi uchun ularni ham o‘chirib tashlash tavsiya etiladi.

Barcha ziddiyatli paketlarni o‘chirish uchun quyidagi buyruqni ishga tushiring:

sudo apt remove $(dpkg --get-selections docker.io docker-compose docker-compose-v2 docker-doc podman-docker containerd runc | cut -f1)


## O‘rnatish usullari

Docker Engine'ni ehtiyojlaringizga qarab turli usullar bilan o‘rnatishingiz mumkin:

### 1. Docker Desktop for Linux

Docker Engine Linux uchun Docker Desktop tarkibida ham mavjud.

Bu Docker bilan ishlashni boshlashning eng oson va tezkor usuli hisoblanadi.

### 2. Docker APT Repository orqali o‘rnatish

Docker'ning rasmiy APT repozitoriyasini sozlab, Docker Engine'ni o‘rnatishingiz mumkin.

Bu usul ishlab chiqarish (Production) va server muhitlari uchun tavsiya etiladi.

### 3. Qo‘lda o‘rnatish

Docker Engine paketlarini qo‘lda yuklab olib o‘rnatishingiz mumkin.

Bu holda yangilanishlarni (upgrade) ham qo‘lda boshqarishingiz kerak bo‘ladi.

### 4. Convenience Script yordamida o‘rnatish

Docker tomonidan taqdim etilgan maxsus skript yordamida tezkor o‘rnatish mumkin.

⚠️ Ushbu usul faqat test va development muhitlari uchun tavsiya etiladi.

## Litsenziya

Docker Engine Apache License 2.0 litsenziyasi asosida tarqatiladi.

To‘liq litsenziya matni bilan `LICENSE` faylida tanishishingiz mumkin.

## APT Repository orqali Docker o‘rnatish

Yangi serverga Docker Engine'ni birinchi marta o‘rnatishdan oldin Docker'ning APT repozitoriyasini sozlash kerak.

Shundan so‘ng Docker'ni ushbu repozitoriy orqali o‘rnatish va keyinchalik yangilab borish mumkin.

### Docker APT Repozitoriyasini Sozlash

#### Docker'ning rasmiy GPG kalitini qo‘shish

```bash
# Add Docker's official GPG key:
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

#### Docker Repozitoriyasini APT manbalariga qo‘shish

```bash
# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update
```

---

## Docker Paketlarini O‘rnatish

Docker Engine'ning eng so‘nggi versiyasini o‘rnatish uchun quyidagi buyruqni bajaring:

```bash
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---

## Docker Servisini Tekshirish

O‘rnatish yakunlangach, Docker servisi ishga tushganligini tekshiring:

```bash
sudo systemctl status docker
```

Agar Docker ishga tushmagan bo‘lsa, uni qo‘lda ishga tushiring:

```bash
sudo systemctl start docker
```

---

## O‘rnatilganligini Tekshirish

Docker muvaffaqiyatli o‘rnatilganligini tekshirish uchun `hello-world` test image'ini ishga tushiring:

```bash
sudo docker run hello-world
```

Ushbu buyruq Docker Hub'dan test image'ni yuklab oladi va uni container ichida ishga tushiradi.

Container ishga tushgach, ekranga tasdiqlovchi xabar chiqaradi va o‘z ishini yakunlaydi.

---

## Xulosa

Agar yuqoridagi test muvaffaqiyatli ishlagan bo‘lsa, Docker Engine serverga muvaffaqiyatli o‘rnatilgan va ishga tushirilgan hisoblanadi. 🎉

