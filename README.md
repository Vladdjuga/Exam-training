# Підготовка до екзамену

Це репозиторій з конспектом/питаннями до екзамену українською та польською мовами (і не тільки).
Сайт публікується на GitHub Pages автоматично через GitHub Actions.

## Відкрити онлайн

- GitHub Pages: `https://Vladdjuga.github.io/Exam-training/`

Головна сторінка — файл `index.md` (Jekyll перетворює його у HTML під час деплою).

## Як це працює

- Воркфлоу деплою: `.github/workflows/deploy.yml`
- Деплой запускається при `push` у гілку `main`
- GitHub Pages збирає сайт через Jekyll (kramdown), тому працює автогенерація змісту (TOC) та Markdown-розмітка.

## Структура

- `index.md` — основний документ (сторінка сайту)
- `img/` — картинки, які використовуються в документі

## Додавання картинок

1. Поклади файл у `img/`
2. Встав у Markdown, наприклад:

```md
![Waterfall](img/waterfall.png)
```

Або через HTML-тег (якщо треба керувати шириною):

```html
<img src="img/waterfall.png" alt="Waterfall" width="600" />
```

## Оновити сайт

```powershell
git add .
git commit -m "Update notes"
git push
```

Після `push` відкрий вкладку **Actions** у GitHub і дочекайся завершення workflow.

## Налаштування GitHub Pages

У репозиторії GitHub:
- `Settings` → `Pages`
- `Source`: **GitHub Actions**
