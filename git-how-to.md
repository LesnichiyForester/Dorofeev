Генерация ключа в keygen  с типом ed25519 без пароля:

b04-206@raspberrypi:~ $ ssh-keygen -t ed25519 -C "Leoitaksoydet@mail.ru"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/b04-206/.ssh/id_ed25519): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/b04-206/.ssh/id_ed25519.
Your public key has been saved in /home/b04-206/.ssh/id_ed25519.pub.
The key fingerprint is:
SHA256:+DJZrv2i4Ex+Gh7kjQRcmBp+yVY3LxcBoRiQ1Y9yvpc Leoitaksoydet@mail.ru
The key's randomart image is:
+--[ED25519 256]--+
| .+=o  oo..      |
|.oo.oo.o .       |
|.o+.o.+ o .      |
|.. B o + o       |
|  o * . S        |
|   + + =         |
|    B * +        |
|   * =.E.        |
|    *o+..o.      |
+----[SHA256]-----+

Добавление файла .pub в аккаунт GitHub
Переназывание приватной части ключа (далее в командах - PersonalKeyLeo)

Получение публичной части ключей:

b04-206@raspberrypi:~ $ ssh-add -l
256 SHA256:HUg32IB6Nn2DFnlPWKJOblNS+ATSVbWOqeHZWLZq0Ck dorofeev.liu@phystech.edu (ED25519)
256 SHA256:+DJZrv2i4Ex+Gh7kjQRcmBp+yVY3LxcBoRiQ1Y9yvpc Leoitaksoydet@mail.ru (ED25519)

Добавление персонального ключа в ответ:

b04-206@raspberrypi:~ $ ssh-add .ssh/PersonalKeyLeo
Identity added: .ssh/PersonalKeyLeo (Leoitaksoydet@mail.ru)

Проверить подключение, сказать что мы доверяем GitHub:

b04-206@raspberrypi:~ $ ssh -T git@github.com
The authenticity of host 'github.com (140.82.121.4)' can't be established.
ECDSA key fingerprint is SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.
Are you sure you want to continue connecting (yes/no)? 
Warning: Permanently added 'github.com,140.82.121.4' (ECDSA) to the list of known hosts.
Hi LesnichiyForester! You've successfully authenticated, but GitHub does not provide shell access.


Клонирование репозитория:

git clone git@github.com:sshadress
