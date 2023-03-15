# Модуль 6. Ansible

Целью данного модуля является знакомство с системой управления конфигурацией Ansible.

## Предварительные требования

Предполагается, что вы выполнили задания по модулям: 
- [GitHub Actions](https://github.com/digital-academy-devops/github-actions-module)
- [Terraform](https://github.com/digital-academy-devops/terraform-module)


## Задание
1. Если Вы не выполняли [дополнительное задание №3](https://github.com/digital-academy-devops/github-actions-module#%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE) в работе по [GitHub Actions](https://github.com/digital-academy-devops/github-actions-module), сделайте это, чтобы иметь возможность опубликовать собранный образ приложения на Dockerhub.
1. В имеющейся у Вас директории состояния в [terraform-gitops](https://github.com/digital-academy-devops/terraform-gitops) внесите следующие изменения:
   1. Увеличьте количество создаваемых серверов до 5.
   1. Добавьте [целевую группу](https://cloud.yandex.ru/docs/network-load-balancer/concepts/target-resources) включающую созданные серверы.
   1. Добавьте [сетевой балансировщик нагрузки](https://cloud.yandex.ru/docs/network-load-balancer/) для балансировки запросов на 80 порт (http) для созданной целевой группы.
  
  Пример PR: https://github.com/digital-academy-devops/terraform-gitops/pull/43
  
1. Реализуйте Playbook, осуществляющий развертывание контейнера приложения на серверах, созданных в пункте 1.2.
   1. Адреса серверов должны быть доступны в выходных значениях (outputs) terraform и статически добавляются в inventory.
   1. После развертывания, страница приложения доступна через адрес сетевого балансировщика (доступен в выходных значениях terraform)
   1. Данное задание не предполагает написание кода который может быть многократно переприменён на управляемых серверах, т.к. это требует более сложной реализаии. Реализация подобного подхода выполняется по желанию и крайне приветствуется :wink:

# Документация
- [Пример](https://github.com/digital-academy-devops/ansible-example) ansible-playbook, реализованный на лекции.
  
  Код примера развертывает контейнер nginx, Вам необходимо внести изменения для развертывания Вашего приложения через docker-compose, по аналогии с [заданием](https://github.com/digital-academy-devops/docker-compose-module) выполненным ранее, за исключением контейнера-балансировщика.
- [Официальная документация Ansible](https://docs.ansible.com/ansible/latest/getting_started/index.html)
- [Репозиторий с примерами playbook-ов](https://github.com/ansible/ansible-examples)
- [Полный список модулей Ansible](https://docs.ansible.com/ansible/2.9/modules/list_of_all_modules.html)
- [Параметры inventory-файла](https://docs.ansible.com/ansible/2.6/user_guide/intro_inventory.html#list-of-behavioral-inventory-parameters)
