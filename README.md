# [Momo Store aka Пельменная №2](https://www.kudelich-store.site)

<img width="900" alt="image" src="https://user-images.githubusercontent.com/9394918/167876466-2c530828-d658-4efe-9064-825626cc6db5.png">

# Сайт магазина
https://www.kudelich-store.site

# Устройство репозитория, внесение изменений и версионирование.
В репо лежат backend и frontend сервисы приложения.

После внесения изменений, пайплайн проекта собирает сервисы, тестирует их(sast, sonarqube, unit-тесты), создаёт докер образы и пушит их в гитлабовский container registry под версией ``1.0.{PipelineId}``.<br> 
Если изменения попадают в ветку main, то в инфраструктурном проекте обновляются до актуальной версии(``1.0.{PipelineId}``) helm-чарты и эти чарты отправляются в нексус репозиторий. Далее их подхватывает развёрнутый в k8s-кластере ArgoCD и обновляет все сервисы.

# Инфраструктура и развёртывание
[Ссылка на проект с инфраструктурой](https://github.com/kostya-kudelich/devops-momo-infrastructure)
