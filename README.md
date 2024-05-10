Домашка для Otus
2й урок
1. #Проверяем какое ядро установлено
vagrant@ubuntu-focal:~$ uname -r
5.4.0-181-generic  #версия ядра
2. На сайте https://kernel.ubuntu.com/mainline/v6.8/ найдена нужная версия ядра, RC обходим мимо :)
3. Устанавливаем утилиту mainline для обновления ядра
4. vagrant@ubuntu-focal:/$ mainline check
mainline 1.4.10
Updating Kernels...
Latest update: 6.8.8 # последняя стабильная версия ядра
Latest point update: 5.4.275
mainline: done
# с помощью mainline можно проверить версию и установить ту что необходимо
#install-latest      Install the latest mainline kernel
#install <names>     Install the specified kernels(1)(2)
#download <names>    Download the specified kernels(1)
5. Ядро ОС обновлено
vagrant@ubuntu-focal:~$ uname -r
6.8.8-060808-generic