## Теоретическое Задание 2

### Вариант 5

**Сравните зарубежных и российских облачных провайдеров. Есть уникальные сервисы и у первых, и у вторых. Что бы вы предложили разместить в частном облаке, что в русском публичном, а что в зарубежном?**

Сравнивая зарубежные и отечественные сервисы: Yandex Cloud смог сопоставить более 30 сервисов, по функционалу дублирующих AWS, однако например AmazonAppStream позволяющий разработчикам и пользователям запускать приложения на любом устройстве без необходимости установки программного обеспечения у Яндекса находится только на стадии разработки, и функции запуска приложений пока вообще нет. Также отсутствует и аналог AWSCodePipeline, который позволяет автоматически тестировать и развёртывать приложения.

У отечественного Яндекса есть Yandex Cloud Functions - сервис, позволяющий без создания и обслуживания виртуальных машин запускать код приложения в виде функции в безопасном, отказоустойчивом и автоматически масштабируемом окружении. Система автоматически выделяет необходимые ресурсы, исходя из заданных в коде параметров.

Также есть интересная система хранилищ в VK Cloud: данные делятся на горячие(доступ к которым требуется всё время и всем пользователям) и холодные, доступ к которым требуется заметно реже. Соответственно, для “горячих” файлов используется hot хранилище. Для “холодных” данных используется более дешёвое “холодное” хранение. Для самых редко используемых - “ледяное”. В Mail Cloud Solutions есть 3 типа облачных сервисов для хранения данных: Hotbox, IceBox и Glacier. (горячее, холодное и ледяное)

Мы предлагаем разместить в зарубежном облаке сервера для онлайн-магазина, так как расположение сервера будет играть очень важную роль. Если основная аудитория расположена например в Финляндии, то будет удобнее расположить сервер там, чтобы не было задержек в передаче данных. Можно также разместить в зарубежном облаке резервное хранилище данных(если отечественный упадёт, то можно будет восстановить данные из зарубежного дата-центра).

В частном облаке целесообразно размещать те данные, которые нуждаются в высокой степени защиты, такие как банковская или медицинская информация, пароли… 

В отечественном публичном облаке можно было бы разместить как раз таки сервера например, сети отечественных продуктовых (или просто) магазинов, где пользователи могут заказывать онлайн: время на обработку будет меньше, так как основная аудитория находится там же.
