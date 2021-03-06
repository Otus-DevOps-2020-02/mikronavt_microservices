# mikronavt_microservices
mikronavt microservices repository

# Домашнее задание 12

### Основное задание:

Установлен docker.
Сделана возможность разворачивать контейнер docker с установленным приложением.
Создан образ docker с установленным приложением.

# Домашнее задание 13

### Основное задание:

Созданы Dockerfile для приложения, разбитого на микросервисные компоненты.
Проверена работа приложений, при запуске в контейнерах docker.

# Домашнее задание 14

### Основное задание:

Проверен запуск docker контейнеров при с разными драйверами сети - none, host и bridge.
Настроен запуск контейнеров с сервисами с помощью docker-compose.
Docker-compose изменен для работы сервисов в двух сетях - back_net и front_net.
В docker-compose файле параметризованы версии приложений, версия mongodb и путь к volume для БД.
Ответ на вопрос:
Префикс перед названием создаваемых docker-compose сущностей - это параметр project-name. По умолчанию задается имя директории, чтобы задать при запуске надо указать параметр -p, например: docker -p 'Test' up.

# Домашнее задание 15

### Основное задание:

На виртуальной машине развернут Gitlab CI.
Добавлено приложение.
Создан пайплайн для приложения, состоящий из этапов: dev, stage, production.
Создано окружение для пайплайна, сделано динамическое окружение для новых веток кода.

# Домашнее задание 16

### Основное задание:

На виртуальной машине с помощью docker развернут prometheus.
Создан docker образ prometheus.
Развернуты микросервисы и prometheus, мониторящий состояние микросервисов.
В prometheus добавлен node exporter, для сбора информации о хосте.
Все образы сохранены в docker hub:
https://hub.docker.com/u/mikronavt

# Домашнее задание 17

### Основное задание:

Мониторинг выделен в отдельный docker compose файл.
Добавлен в конфиги, развернут и протестирован сервис cAdvisor.
Добавлена в конфиги, развернута и протестирована Grafana.
В Grafana импортирован дашборд 'docker and system monitoring'.
Создан дашборд Grafana, содержащий графики, показывающий характеристики Http запросов.
Создан дашборд Grafana, содержащий бизнес-метрики.
Добавлен в конфиги, развернут и протестирован сервис Alertmanager, настроены оповещения в slack.
Все образы сохранены в docker hub:
https://hub.docker.com/u/mikronavt

# Домашнее задание 18

### Основное задание:
Развернута обновленная версия приложения, настроенная на логирование.
Создан и развернут образ Fluentd с EFK стеком.
Для сервиса post настроена отправка логов во fluentd.
Проверена работа Kibana и поиск логов.
Во fluentd добавлен фильтр для парсинга json логов от сервиса post.
Для сервиса ui настроена отправка логов во fluentd.
Во fluentd добавлен парсинг логов от сервиса ui на основе grok-шаблонов.
Добавлен, развернут и проверен сервис трейсинга Zipkin.

# Домашнее задание 19

### Основное задание:
Созданы файлы deployment-манифестов приложений для kubernetes.
Развернут вручную путем "The hard way" кластер Kubernetes.
Все файлы, созданные в процессе развертывания, сохранены в /kubernetes/the_hard_way

# Домашнее задание 20

### Основное задание:
Установлен локально kubectl и minikube, запущен кластер minikube.
Созданы деплоймент-файлы для модулей приложения ui, comment, post и для mongodb.
В кластере развернуто приложение reddit app.
Добавлены сервисы для связи между модулями приложения.
Добавлен сервис для доступа к приложению извне кластера.
Проверена работа аддона dashboard.
Создан namespace dev и приложение развернуто в неймспейсе.
Информация об окружении добавлена внутрь контейнера ui.
Развернут kubernetes-кластер в GKE и приложение задеплоено в нём.
Развернут dashboard в кластере GKE.

# Домашнее задание 21

### Основное задание:
Проверено нарушение работы приложения при отключении kube-dns.
Сервис UI настроен на работу с LoadBalancer-ом.
Настроена работа приложения с Ingress controller-ом.
Настроены NetworkPolicy, позволяющие обращаться к mongodb только с pod-ов post и comment.
Настроено хранение данных БД в диске Coogle Cloud, в Persistent Vlolume, в динамическом PVC.

# Домашнее задание 22

### Основное задание:
Установлены Helm, Tiller.
Созданы Chart-ы для установки приложений с помощью Helm.
Шаблонизированы .yaml-сущности для установки приложений.
Созданы шаблоны для задания адреса БД.
Созданы функции-хелперы получения имени приложений, вынесены в файлы _helpers.tpl.
Создан Chart reddit для управления установкой всех приложений.
Переменные окружения с адреами серверов добавляются при деплое.
Проверен деплой в нужный namespace с помощью tiller-плагина.
Проверено развертывание приложения с помощью helm весрии 3.
Установлен Gitlab с помощью Helm.
Создана группа и проекты ui, comment, post, reddit-deploy а гитлабе.
В проекты ui, post, comment добавлены исходники приложений, в проект reddit-deploy - Chart-ы.
Добавлены файлы .gitlab-ci.yml для сборки приложений в гитоабе.
Настроен CI для приложений.
Настроен деплой приложений.
Изменены файлы .gitlab-ci.yml для соответствия синтаксису Gitlab.
Пайплайн для COMMENT настроен для деплоя с помощью tiller-плагина.
Пайплайн для POST настроен для деплоя с помощью Helm 3.

# Домашнее задание 22

### Основное задание:
С помощью Helm чарта установлен Prometheus.
В Prometheus включили сервис kube-state-metrics и поды node-exporter.
Добавлены эндпоинты для сбора метрик с приложений.
Настроен сбор метрик по окружениям и по компонентам приложения.
С помощью Helm установлена graphana.
В графане загружен дашборд Kubernetes cluster monitoring (via Prometheus).
Загружены в графану сделанные в предыдущих ДЗ дашборты и шаблонизированы, выгруженные дашборды в директории kubernetes/dashboards.
В графану импортирован и проверен график Kubernetes Deployment metrics.
Установлен EFK  стек и проверена его работа в кластере.
