# Завдання: Створення матеріалів для висвітлення як працює Claude Code

## Що буде створено

- Кластер k8s на AWS EKS з допомогою Terraform
- Налаштування Cloudflare з допомогою Terraform
- Проста HTML гра
- Helm Chart для розгортання гри на Kubernetes
- Розгортання гри
- Надання публічного доступу

## Створення репозиторіїв

Створи публічні репозиторії з допомогою GitHub CLI:

```bash
gh repo create <ім'я_репозиторію> --public --description "<опис_репозиторію>"
```

### Назви репозиторіїв

- `hl-eks-terraform`
- `hl-cloudflare-terraform`
- `hl-game-html`
- `hl-helm-chart`

## Задачі для кожного репозиторію

### 1. hl-eks-terraform

- Створи Terraform конфігурацію для створення EKS кластера з однією автоскейл групою
- Версія кластера: **1.33**
- Назва кластера: `hl-game-cluster`
- Використовуй terraform провайдер: https://registry.terraform.io/modules/terraform-aws-modules/eks/aws/latest
- Використовуй AWS профіль: `claude-aws`
- Встановити nginx-ingress контролер на кластер після створення (використовувати класичний балансувальник)
- Додай README файл з інструкціями з розгортання

### 2. hl-cloudflare-terraform

- Створи Terraform конфігурацію для налаштування Cloudflare (створення DNS запису)
- Використовуй офіційний Cloudflare Terraform провайдер
- Використовуй `@gmail.com` Global API Key та ZonaID
- Клади ці секрети в `.auto.tfvars`, який повинен бути в `.gitignore`
- Домен для гри: `cball.media.pp.ua`

### 3. hl-game-html

- Створи просту HTML гру (опис в [game.md](game.md))
- Зібрати Docker image і запушити на https://hub.docker.com/u/infrapublic

### 4. hl-helm-chart

- Створи Helm Chart за допомогою команди: `helm create hl-game-html`
- Внеси зміни в створений Helm Chart для розгортання гри з hl-game-html на Kubernetes
- Використовуй nginx-ingress контролер, який був створений
- Додай README файл з інструкціями по встановленню Helm Chart