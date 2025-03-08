# Портфолио
## Описание
* Данный репозиторий содержит ссылки на другие репозитории.  
* Конечная цель проекта - создание инфраструктуры разработки с использованием kubernetes и gitlab.  
* Для хранения репозиториев была создана тестовая организация [FZEN475](https://github.com/orgs/FZEN475)  
* Все репозитории зеркалируются из закрытого gitlab.  

## Список репозиториев.
* Подготовка инструментов.
  * [Образ multitool](https://github.com/FZEN475/multitool.git)
  * [Образ terraform](https://github.com/FZEN475/terraform-image)
  * [Образ ansible](https://github.com/FZEN475/ansible-image)
  * [Библиотеки ansible](https://github.com/FZEN475/ansible-library)
  * [Настройки агентов KAS](https://github.com/FZEN475/kubernetes-agent-config.git)
  * [Библиотеки ci](https://github.com/FZEN475/ci-library)
* Подготовка инфраструктуры.
  * [Установка PXE](https://github.com/FZEN475/PXE)
  * [Terraform](https://github.com/FZEN475/terraform)
  * [Общий софт](https://github.com/FZEN475/common-soft.git)
  * [docker-swarm](https://github.com/FZEN475/swarm.git)
  * [kubernetes](https://github.com/FZEN475/kubernetes.git)
* [Поставщики.](https://github.com/FZEN475/kubernetes-provisioners.git)
* [Хранилища](https://github.com/FZEN475/kubernetes-storages.git)
* [gitlab](https://github.com/FZEN475/kubernetes-gitlab.git)

## Оборудование и инфраструктура
### Оборудование

| Оборудование | OS                | Processor        | RAM   | SSD          | Comment |
|--------------|:------------------|------------------|-------|--------------|---------|
| Asus RT-N16  | OpenWRT           | Broadcom BCM4718 | 128Mi | 32Mi + 512Gi |         | 
| server       | esxi 7.0 Update 1 | i7-4770K         | 32Gi  | 250Gi+125Gi  |         |

### Основной софт

| Инфраструктура | Version      | Comment                               |
|----------------|:-------------|---------------------------------------|
| esxi           | 7.0 Update 1 | Виртуализация основных NOD            | 
| OpenWRT        | 23.05.5      | PXE, NAS, Хранение бекапов            |
| terraform      |              | Управление виртуальными машинами esxi |
| ansible        | 2.2.4        | Развёртывание до gitlab               |
| keepalived     | 2.2.4        | balanser                              |
| Doker swarm    | 27.4.0       | etcd, nginx-balanser                  |
| kubernetes     | 1.31.3       |                                       |

### Kubernetes

| Инфраструктура              | Comment                         |
|-----------------------------|:--------------------------------|
| calico                      | Сеть и сетевая безопасность     |
| nfs-provisioner             | Внешнее сетевое хранилище       | 
| cert-manager, trust-manager | Управление сертификатами        |           
| vault                       | Управление паролями             | 
| reloader                    | Автоматическая перезагрузка POD |   
| ingress-nginx               | Внешний endpoint                |  
| prometheus, grafana         | Внешний endpoint                |  
| gitlab, gitlab-ci           | Управление кодом                |  

| Хранилища     | Comment                         |
|---------------|:--------------------------------|
| minio         | S3 хранилище                    |
| pgsql         | База данный                     | 
| registry      | Хранение docker image           |           
| redis         | RAM база данных                 | 


