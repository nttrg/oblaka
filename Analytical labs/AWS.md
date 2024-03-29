# Аналитическая работа 1

### Состав команды

- [Крашенинникова Дарья](https://t.me/CrashDari) 
- [Таргович Наталья](https://t.me/natarg) 

### Цель работы
Знакомство с облачными сервисами. Понимание уровней абстракции над инфраструктурой в облаке. Формирование понимания типов потребления сервисов в сервисной-модели. Сопоставление сервисов между разными провайдерами. Оценка возможностей миграции на отечественные сервисы.

### Дано
Слепок данных биллинга от провайдера после небольшой обработки в виде SQL-параметров. Символ % в начале/конце означает, что перед/после него может стоять любой набор символов.
![начальные данные AWS](https://github.com/nttrg/oblaka/assets/113716100/00ecb727-8e70-4385-8475-df9021598b9a)


### Описание сервисов


**APNFee** - сервис, где партнёры могут получить доступ к программам AWS. С помощью него партнёры могут запросить коммерческую или маркетинговую поддержку.

---

**AmazonAppStream** - это облачный сервис, который позволяет разработчикам и пользователям запускать приложения на любом устройстве без необходимости установки программного обеспечения. 
   1. Stream - это функция Amazon AppStream, которая позволяет пользователям получать доступ к своим приложениям в режиме реального времени без необходимости устанавливать их на своем устройстве. Stream также позволяет пользователям управлять своими приложениями, обновлять их и удалять их с устройства.
   2. Amazon AppStream StoppedInstance - это состояние экземпляра Amazon AppStream, который был остановлен. В этом состоянии экземпляр не может принимать подключения от пользователей, но все еще занимает ресурсы в облаке Amazon.
   3. Win-User - это функция, которая позволяет пользователям запускать Windows-приложения в облаке и использовать их на любом устройстве. Эта функция позволяет пользователям получить доступ к своим рабочим столам и приложениям с любого устройства, подключенного к Интернету, без необходимости установки приложений на каждом устройстве.

---

**AmazonAthena** -  это облачный сервис который позволяет бессерверные запросы к содержимому который хранится на AWS S3. Поддерживает различные форматы данных, такие как CSV, TSV, и JSON а также данные в форматах столбцов и сжатые данные.

 1. Amazon Athena DataScanned - это метрика, которая показывает количество данных, которые были просканированы с помощью сервиса Amazon Athena. Этот показатель может использоваться для мониторинга активности сканирования данных и определения производительности запросов.
 2. Amazon Athena Requests-Tier1 - это уровень обслуживания запросов в сервисе Amazon Athena, который предназначен для обработки высокопроизводительных запросов. Этот уровень обеспечивает более высокую пропускную способность и меньшую задержку по сравнению с другими уровнями обслуживания.
---

**AmazonCloudDirectory** - это сервис для управления иерархическими структурами данных, такими как каталоги, деревья, структуры XML и другие. Он позволяет создавать, изменять и удалять элементы в структуре, а также искать и фильтровать данные по различным критериям.
  1. Amazon Cloud Directory Requests-Tier1 - это уровень обслуживания запросов для высокопроизводительных операций в Amazon Cloud Directory. Этот уровень предлагает более высокую пропускную способность и меньшее время отклика по сравнению с другими уровнями.
  2. Requests-Tier2 - это уровень обслуживания, который предлагает средний уровень обслуживания, с меньшим количеством поддержки и более медленным временем отклика.

---

**AmazonDocDB** - сервис баз данных, который упрощает настройку, эксплуатацию и масштабирование баз данных, совместимых с MongoDB.
   1.  InstanceUsage - это параметр, который показывает, как используется база данных. Он включает информацию о процессоре, памяти и диске. Этот параметр может помочь вам определить, насколько эффективно используется ваша база данных и нужно ли её масштабировать.
   2. StorageIOUsage - это метрика, которая показывает количество операций чтения и записи, которые были выполнены на дисках базы данных AmazonDocDB.
   3. StorageUsage - это метрика, которая отображает количество свободного и занятого места на дисках базы данных AmazonDocDB. Позволяет оценить, сколько места уже использовано и сколько еще доступно для хранения данных.
   4. BackupUsage - это метрика, которая показывает сколько резервных копий было создано и использовано для базы данных AmazonDocDB. С помощью этого параметра можно оценить, сколько места было сэкономлено благодаря использованию функции резервного копирования, а также определить, когда необходимо создать новую резервную копию.

---

**AmazonEI** - то сервис, который позволяет пользователям подключать ускорение логического вывода на базе GPU к экземплярам Amazon EC2. Этот сервис предназначен для того, чтобы помочь пользователям оптимизировать свои приложения машинного обучения.
   1. AmazonEI eia1 - это уровень сервиса обработки естественного языка от Amazon. Уровень eia1 предоставляет более высокую производительность и большее количество транзакций по сравнению с другими уровнями сервиса.
   2. AmazonEI eia2 - это уровень сервиса обработки естественного языка от Amazon. Он также предлагает различные функции, но с немного меньшей производительностью и количеством транзакций, чем eia1.

---

**AWSIoT** - платформа, которая собирает и обрабатывает данные с подключенных к Интернету устройств и датчиков и связывает их с облачными приложениями AWS.
   1. AWSIoT Messages - это количество сообщений, которые были отправлены и получены через сервис AWS IoT. Этот параметр позволяет оценить активность использования сервиса и определить, нужно ли увеличивать его ресурсы для обработки большего количества сообщений.
   2. RegistryAndShadowOperations - это количество операций, которые были выполнены над реестрами и тенями в сервисе AWS IoT. Эти операции включают создание, обновление, удаление регистров и теней, а также выполнение запросов к ним. Данный параметр помогает оценить активность использования сервиса и необходимость масштабирования его ресурсов для выполнения большего количества операций.
   3. ConnectionMinutes - это объем времени, в течение которого были активны соединения с сервисом AWS IoT.
   4. MQTT - это протокол, который используется для связи с сервисом AWS IoT. Он позволяет клиентам отправлять и получать сообщения от сервиса, а также выполнять различные операции с реестрами и тенями.

---

**IoTDeviceManagement** - это функция AWS, которая позволяет управлять устройствами IoT, такими как датчики, актуаторы и другие устройства. Она предоставляет возможности для настройки, мониторинга и управления устройствами, а также для сбора и анализа данных.
   1.  IndexedData - это количество данных, которые были проиндексированы с помощью сервиса IoTDeviceManagement. Этот параметр помогает оценить, сколько данных было обработано и сколько времени потребовалось для индексации.

---

**AWSCodePipeline** - это инструмент для автоматизации процесса развертывания приложений. Он позволяет автоматически создавать, тестировать, обновлять и развертывать приложения. С его помощью можно настроить автоматическую сборку кода, тестирование, а также развертывание на разных серверах в зависимости от результатов тестирования.
   1.  trialPipeline - это тестовая конвейерная система, которая позволяет разработчикам создавать, тестировать и развертывать свои приложения. Она включает в себя множество инструментов и сервисов, таких как AWS CodeCommit, AWS CodeBuild, AWS CodeDeploy.
   2.  activePipeline - это активная конвейерная система, которая используется для разработки, тестирования и развертывания приложений. Позволяет разработчикам управлять своими конвейерами, обновлять их и добавлять новые этапы.

---

**AWSXRay** - это сервис, который собирает данные о запросах, обслуживаемых вашим приложением, и предоставляет инструменты, которые вы можете использовать для просмотра, фильтрации и получения подробной информации об этих данных для выявления проблем и возможностей оптимизации.
   1. X-Ray - это служба AWS, которая помогает анализировать производительность приложений и обнаруживать проблемы. Она позволяет отслеживать запросы, поступающие в приложение, и определять, какие компоненты работают медленно или вызывают ошибки. 

---

**CodeBuild** - это полностью управляемый сервис сборки в облаке. CodeBuild компилирует исходный код, запускает модульные тесты, готовые к развертыванию. CodeBuild устраняет необходимость в подготовке, управлении и масштабировании собственных серверов сборки.

---

**AmazonML** - это облачный сервис для создания и использования моделей машинного обучения. 
   1. AML BoxUsage - это метрика, показывающая использование ресурсов AML Box, включая процессорное время, объем используемой памяти и количество операций ввода-вывода.
   2. Batch Prediction Chunk - это часть пакета, который выполняется с использованием сервиса Amazon Machine Learning. Содержит данные, которые используются для определения пакета, который подходит лучше, а также информацию о том, какой моделью машинного обучения следует воспользоваться.
   3. AMLBoxUsage_TrainModel - это метрика, которая отражает использование ресурсов Amazon Machine Learning во время **обучения** модели машинного обучения. Содержит информацию о времени процессора, объеме используемой памяти и количестве операций ввода-вывода, необходимых для обучения модели.
   4. AMLBoxUsage_EvaluateModel - это метрика, которая отражает использование ресурсов Amazon Machine Learning при **оценке** модели машинного обучения. Включает информацию о времени процессора, используемой памяти и операциях ввода-вывода во время оценки модели.

---

**AmazonPolly** - это облачный сервис, который преобразует текст в реалистичную речь.

---

**AmazonPersonalize** - это облачный сервис, предназначенный для персонализации рекомендаций, таргетированной рекламы и других видов маркетинга. Он использует алгоритмы машинного обучения для анализа данных и создания персонализированных рекомендаций.
   1. TPS-hours - это метрика, которая измеряет количество транзакций в секунду, умноженное на количество часов, в течение которых Personalize сервис был активен.
   2. TrainingHour - это метрика, которая показывает количество часов, затраченных на обучение моделей персонализации.
   3. Data Ingestion - это процесс загрузки данных в сервис Amazon Personalize. Этот процесс включает в себя сбор данных из различных источников, их очистку и преобразование в формат, понятный для Personalize. 
---

**AmazonRekognition** - это сервис компьютерного зрения, который позволяет распознавать объекты, лица, текст и другие элементы на изображениях и видео.

---

**AmazonEC2**  - это сервис, который предоставляет вычислительные мощности путем предоставления виртуальных машин с заранее созданными образами операционных систем.
   1. EBS  Volume IO Usage - это метрика, которая показывает объем операций ввода-вывода, выполненных на томах EBS. Она включает как чтение, так и запись данных. Может помочь оценить, насколько активно используются тома EBS, и определить, необходимо ли увеличение их производительности.
   2. EBS Snapshot Usage Under Billing - это метрика, которая показывает, сколько места на снимках EBS используется, но не учитывается в биллинге. 
   3. EBS Volume Usage - это метрика, которая показывает использованный объем томов EBS. Эта метрика позволяет оценить, сколько места занято данными и сколько еще можно использовать для хранения информации.
   4. EBS Snapshot Usage - это метрика, которая показывает используемый объем снимков EBS. Этот параметр позволяет оценить, сколько места занимают снимки и сколько еще места можно использовать для создания новых снимков.
   5. EBS Volume Provisioned IOPS - это метрика, которая показывает количество операций ввода-вывода в секунду (IOPS), выделенных для тома EBS. Параметр позволяет контролировать и оптимизировать производительность томов EBS, а также планировать расширение или сокращение ресурсов в зависимости от текущих потребностей.

---


### Маппинг

| Type                              | Product Code               | Yandex Cloud                      |
|-----------------------------------|----------------------------|-----------------------------------|
| Partner program                   | APNFee             | Yandex Cloud (Professionals)              |
| Application streaming             | AmazonAppStream             | nope                             |
| Data analytics service            | AmazonAthena    | Yandex DataLens  |
| Managing  directories             | AmazonCloudDirectory              |     nope  |
| NoSQL                  | AmazonDocDB             |  Yandex Managed Service for MongoDB                           |
| Attach GPU-powered inference acceleration to Amazon EC2 instances         | AmazonEI              | nope               |
| The Internet of Things platform                 | AWSIoT        | Yandex  IoT Core                  |
|Function of IoT device management | IoTDeviceManagement |	Yandex IoT Core(в функционале)|
|automation of application development and deployment|	AWSCodePipeline	|nope|
|debugging and monitoring application performance	|AWSXRay	|Yandex  Application Load Balancer(есть возможность анализа)|
| Build service	|CodeBuild	|nope|
|Machine learning service	|AmazonML |	Yandex DataSphere|
|Сonverting text to life like speech|	AmazonPolly|	Yandex SpeechKit|
|Рroduct and service recommendation service|	AmazonPersonalize	|nope|
|Image recognition service|	AmazonRekognition|	Yandex Vision|
|Managing virtual machines|	AmazonEC2	|Yandex Compute Cloud|

### Описание сервисов Yandex Cloud 
Yandex Cloud (Professionals) - это облачная платформа с цифровыми связными сервисами, где можно создать и развивать бизнес-проекты и упрощать бизнес-процессы. Облако даёт возможность использовать инфраструктуру и технологии Яндекса.

---

Yandex DataLens - это сервис для бизнес-аналитики. Сервис позволяет подключаться к различным источникам данных, строить визуализации, собирать дашборды и делиться полученными результатами.

---

Yandex Managed Service for MongoDB - это сервис, который разворачивает готовую к эксплуатации базу данных на основе СУБД **MongoDB**, управляет ею и обновляет.

---

Yandex  IoT Core - это облачный сервис для управления устройствами интернета вещей (IoT). Он позволяет регистрировать устройства, создавать правила обработки данных, а также управлять доступом к данным.

---

Yandex  Application Load Balancer - это сервис, который помогает распределять нагрузку на веб-приложения. Он балансирует входящий трафик между различными компонентами приложения, чтобы улучшить производительность.

---

Yandex DataSphere - сервис для анализа данных, разработки и эксплуатации моделей машинного обучения.

---

Yandex SpeechKit - сервис, который позволяет разработчикам приложений использовать речевые технологии Яндекса: распознавание речи (Speech-to-Text) и синтез речи (Text-to-Speech).

---

Yandex Vision - сервис визуальной аналитики, позволяющий реализовывать распознавание текста и объектов на изображениях с помощью программных моделей машинного обучения.

---

Yandex Compute Cloud - сервис, который предоставляет масштабируемые вычислительные мощности для создания виртуальных машин и управления ими.

### Вывод
В ходе выполнения данной работы мы ознакомились с сервисами Amazon, а также провели сравнение и сопоставили сервисам Amazon сервисы Yandex Cloud. Аналоги были найдены не для всех сервисов. Вывод: миграция возможна, однако в том случае, когда аналоги сервисов Amazon в Yandex Cloud полностью покрывают требуемые функции.
