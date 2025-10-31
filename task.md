# Завдання: Створення матеріалів для висвітлення як працює claude code

Буде створенный:
   - кластер k8s на AWS EKS з допомогою Terraform.
   - налаштування Cloudflare з допомогою Terraform.
   - проста HTML гра.
   - Helm Chart для розгортання гри на Kubernetes.
   - розгортання гры
   - надання публичного доступу


Створи публічні репозиторії з допомогою GitHub cli `gh repo create <ім'я_репозиторію> --public --description "<опис_репозиторію>"`.
Назви репозиторії відповідно:
 - hl-eks-terraform
 - hl-cloudflare-terraform
 - hl-game-html
 - hl-helm-chart

Задачі для кожного репозиторію:
1. hl-eks-terraform:
   - Створи Terraform конфігурацію для створення EKS кластера з однією автоскейл групою. Версія кластера 1.33. назва кластера `hl-game-cluster`.
   - Використовуй terraform провайдер https://registry.terraform.io/modules/terraform-aws-modules/eks/aws/latest
   - Використовуй AWS профіль `claude-aws`.
   - Встановити nginx-ingress контролер на кластер після створення. Використовувати потрібно классичный балансувальник
   - Додай README файл з інструкціями з розгортання.

2. hl-cloudflare-terraform:
   - Створи Terraform конфігурацію для налаштування Cloudflare (наприклад, створення DNS запису).
   - Використовуй офіційний Cloudflare Terraform провайдер.
   - Використовуй --------------@gmail.com Global API Key: --------------- ZonaID: ---------------- клади ці секрети в .auto.tfvars який в свою чергу повинен буди в .gitignore.
   - Домен буде для гри з hl-game-html. cball.media.pp.ua

3. hl-game-html:
   - Створи просту HTML гру [game.md](game.md).
   - зібрати docker image і запушити https://hub.docker.com/u/infrapublic (docker hub infrapublic я вже залогінився )

4. hl-helm-chart:
   - Створи Helm Chart "helm create hl-game-html" для розгортання гри з hl-game-html на Kubernetes.
   - Внеси зміни в створений Helm Chart
   - Використовуй nginx-ingress контролер який був створенний 
   - Додай README файл з інструкціями по встановленню Helm Chart.

 