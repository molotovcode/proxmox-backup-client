## proxmox-backup-client

Установка proxmox backup client для бэкапа файлов с удаленных хостов

## Требования
для поддержки namespaces требуется Debian 11

к машине открыт доступ через ssh по паролю

на машине установлен пакет sudo

локальный пользователь на машине включен в группу sudo

## Выполнение
`ansible-playbook pbclient.yml -i <host>, --ask-pass -u <user> --ask-become-pass`

в процессе выполнения плейбука необходимо ввести директорию для бэкапирования, пример: /mnt/data/example для бэкапа нескольких директорий вводим /mnt/data/example root.pxar:/mnt/data2/example2 указание root.pxar: важно!

## Подстановка данных из bitwarden
Для подстановки паролей и иных данных из Bitwarden перед запуском playbook необходимо выполнить:

```
bw logout
bw config server bitwarden
export BW_SESSION="$(bw login --raw)"
```
