# Описание

Данный репозиторий предназначен для написания шаблонов, которые могут задействованы для автоматизации внутренних IT-задач.

## Параметры хостов [inventory/hosts]

В репозитории не размещены (.gitignore) такие директории, как:

- group_vars

    в этой директории указаны файлы групп хостов, в которых содержится информация о одинаковых параметрах хостов (username, become password, путь до ssh-ключа)

- host_vars

    в этой директории указаны файлы по каждому необходимому хосту, в которых содержится информация о параметрах хоста (username, become password, путь до ssh-ключа)

## Playbook - "Установка golang" [install_golang.yml]

Плейбук отвечает за скачивание релиза golang нужной версии.

-> Выбрать нужный релиз можно в этом [источнике](https://go.dev/dl/).

Скопировать релиз и изменить параметры плейбука:

```yml
    go_download_url: "https://go.dev/dl/<release>"

    go_tar_file: "<release>"
```

## Playbook - "Настройка параметров конфига" [change_config.yml]

Плейбук отвечает за изменение параметров конфига построчно.

Создаем необходимые для себя таски, изменяем параметры: 

```yml
    path: "<path to config file>"

    regexp: '<parameter>:.*'

    replace: '<parameter>: <parameter value>'
```

## Конфиденциальность [ansible-vault]

Важно отметить, что для публикации файлов конфигурации необходимо избегать использование внутренних параметров проекта, таких как:
- IP-адрес хоста
- Учётные данные (имя пользователя, пароль)
- ssh-ключи
и др..

Ansible-vault - это инструмент, который позволяет шифровать и расшифровывать данные, такие как данные о хостах (имя пользователя, пароль, ip-адрес) и ключи, используемые в плейбуках Ansible. Это полезно для защиты конфиденциальной информации, которая не должна храниться в открытом виде репозиториях кода.

## Ansible

Ansible — это простой в использовании, мощный инструмент для автоматизации IT-задач. Он позволяет управлять конфигурацией, развертывать приложения и оркестрировать сложные рабочие процессы. Ansible использует простой язык YAML для описания автоматизированных задач в виде "плейбуков".

## Документация

Полная документация доступна на [официальном сайте Ansible](https://docs.ansible.com/).

## Test text dev branch
