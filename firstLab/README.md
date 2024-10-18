# Лабораторная работа №1

Выполнил: Алексеев Николай, К3244

## Задача лабораторной:

Настроить nginx по заданному тз:
  1. Должен работать по https c сертификатом
  2. Настроить принудительное перенаправление HTTP-запросов (порт 80) на HTTPS (порт 443) для обеспечения безопасного соединения.
  3. Использовать alias для создания псевдонимов путей к файлам или каталогам на сервере.
  4. Настроить виртуальные хосты для обслуживания нескольких доменных имен на одном сервере.
  5. Что угодно еще под требования проекта

## Ход работы

Для того, чтобы настроить nginx он должен быть, поэтому устанавливаем его:
  1. Обновляем пакетный менеджер:

![Screenshot 2024-10-08 201337](https://github.com/user-attachments/assets/65d70292-6ffd-4338-a220-70e05cbcc06d)

  2. Устанавливаем nginx:

![Screenshot 2024-10-08 201528](https://github.com/user-attachments/assets/3e1c3e24-44b7-409a-98ef-584ed7a38d76)

Далее, чтобы подключаться к нашему сайту по https нам нужен сертификат, поэтому создаем его и ключ к нему:

![Screenshot 2024-10-08 222437](https://github.com/user-attachments/assets/862ca12f-e8d6-4b43-af13-25c37b534212)

Создаем файлы project007.com и project700.com, в которых прописываем логику перенаправления с 80 на 443 порт, какой сертификат используем для https и корневые папки проектов.

![Screenshot 2024-10-08 223241](https://github.com/user-attachments/assets/a8d94276-1931-4235-a21a-6508ad462da7)

![Screenshot 2024-10-08 223307](https://github.com/user-attachments/assets/192411f6-06d3-4063-af76-8781afbae153)

Создаем простейшие файлики index.html в корневых папках проектов:

![Screenshot 2024-10-17 131004](https://github.com/user-attachments/assets/854c5eed-0e73-4a61-991e-f374133f2a8b)

![Screenshot 2024-10-18 123714](https://github.com/user-attachments/assets/aab2e98d-7500-4e1f-8cd2-1ab48158d236)

Прописываем в /etc/hosts наши доменные имена, чтобы они открывались на нашем сервере.

![Screenshot 2024-10-18 110025](https://github.com/user-attachments/assets/de714ad3-b567-4fe6-a243-e80ffe862c31)

Пишем в браузере доменные имена проектов и надеемся на лучшее:

И не зря надеемся! Проекты не только открываются, но еще и совершают автоматическую переадресацию с http на https:

![Screenshot 2024-10-18 104609](https://github.com/user-attachments/assets/a95fc0eb-2de9-4b33-aa40-e1df4343c506)

![Screenshot 2024-10-18 104632](https://github.com/user-attachments/assets/6dff373c-5eec-4857-90eb-5a521fc0cc75)

![Screenshot 2024-10-18 105008](https://github.com/user-attachments/assets/f2006212-8dc1-4c16-a182-da3c8a7f139b)

![Screenshot 2024-10-18 105028](https://github.com/user-attachments/assets/eec5eea0-b64b-4129-92e3-ae19b53f38f2)

Осталось только добавить alias:

Прописываем alias в файлах проектов:

![Screenshot 2024-10-18 123945](https://github.com/user-attachments/assets/b45f47ed-ea73-42cd-b917-49ca6ee3ee90)

![Screenshot 2024-10-18 123927](https://github.com/user-attachments/assets/6abc3eec-f230-44bd-95b7-477acec7d483)

Создаем файлы в указанных папках и проверяем в браузере работает ли alias:

![Screenshot 2024-10-18 125602](https://github.com/user-attachments/assets/306772b7-338a-4ae1-bdd6-d5f9f7ea9ef1)

![Screenshot 2024-10-18 124024](https://github.com/user-attachments/assets/b6064649-15e2-4b41-890f-8459c86e1f31)

Все прекрасно работает.

## На этом лабораторная окончена, спасибо за внимание!
