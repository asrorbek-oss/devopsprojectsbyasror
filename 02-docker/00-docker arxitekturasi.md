# Docker Nima?

Docker — bu ilovalarni **container** ichida yaratish, tarqatish va ishga tushirish uchun mo'ljallangan platforma.

Containerlar ilova va uning barcha bog'liqliklarini (kutubxonalar, konfiguratsiyalar va boshqalar) bir joyga jamlaydi. Natijada ilova har qanday muhitda bir xil ishlaydi.

## Docker Afzalliklari

* Tez deploy qilish
* Resurslardan samarali foydalanish
* Portativlik (har qanday serverda bir xil ishlaydi)
* Izolyatsiya
* CI/CD jarayonlarini soddalashtiradi

## Docker Arxitekturasi

```text
+--------------------------------------------------+
|                   Docker Host                    |
|                                                  |
|  +-------------------+                           |
|  |   Docker Daemon   |                           |
|  |     (dockerd)     |                           |
|  +---------+---------+                           |
|            |                                     |
|            v                                     |
|  +-------------------+                           |
|  | Docker Images     |                           |
|  +-------------------+                           |
|            |                                     |
|            v                                     |
|  +-------------------+                           |
|  | Docker Containers |                           |
|  +-------------------+                           |
|                                                  |
+--------------------------------------------------+
             ^
             |
      +------+------+
      | Docker CLI  |
      |   docker    |
      +-------------+
```

## Asosiy Komponentlar

### Docker CLI

Foydalanuvchi Docker bilan ishlaydigan buyruq qatori interfeysi.

Misol:

```bash
docker run nginx
docker ps
docker images
```

### Docker Daemon (dockerd)

Dockerning asosiy servisi bo'lib, image va containerlarni boshqaradi.

### Docker Images

Container yaratish uchun shablon hisoblanadi.

Misol:

```bash
docker pull nginx
```

### Docker Containers

Image asosida ishga tushirilgan izolyatsiyalangan muhit.

Misol:

```bash
docker run -d nginx
```

## Docker Workflow

```text
Developer
    |
    v
Dockerfile
    |
    v
docker build
    |
    v
Docker Image
    |
    v
docker run
    |
    v
Container
```

## Xulosa

Docker ilovalarni konteynerlarda ishga tushirish imkonini beruvchi platforma bo'lib, DevOps va Cloud muhitlarida keng qo'llaniladi. Docker yordamida ilovalarni tez, ishonchli va portativ tarzda deploy qilish mumkin.

