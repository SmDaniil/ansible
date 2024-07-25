# Описание

Данный репозиторий предназначен для написания шаблонов, которые могут задействованы для автоматизации внутренних IT-задач.

# Ansible

Ansible — это простой в использовании, мощный инструмент для автоматизации IT-задач. Он позволяет управлять конфигурацией, развертывать приложения и оркестрировать сложные рабочие процессы. Ansible использует простой язык YAML для описания автоматизированных задач в виде "плейбуков".

## Документация

Полная документация доступна на [официальном сайте Ansible](https://docs.ansible.com/).

# Конфиденциальность [ansible-vault]

Важно отметить, что для публикации файлов конфигурации необходимо избегать использование внутренних параметров проекта, таких как:
- IP-адрес хоста
- Учётные данные (имя пользователя, пароль)
- ssh-ключи
и др..

Ansible-vault - это инструмент, который позволяет шифровать и расшифровывать данные, такие как данные о хостах (имя пользователя, пароль, ip-адрес) и ключи, используемые в плейбуках Ansible. Это полезно для защиты конфиденциальной информации, которая не должна храниться в открытом виде репозиториях кода.