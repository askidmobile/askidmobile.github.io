# Askid — статьи и заметки

Исходники личного сайта [askidmobile.github.io](https://askidmobile.github.io). Сайт собирается Jekyll и публикуется через GitHub Pages.

## Как опубликовать статью

1. Скопируйте `_drafts/article-template.md` в папку `_posts/`.
2. Назовите файл по схеме `ГГГГ-ММ-ДД-короткое-название.md`, например `2026-07-30-local-first-ai.md`.
3. Заполните метаданные между строками `---` и напишите текст статьи в Markdown.
4. Закоммитьте файл и отправьте изменения в ветку `main`.

Пример команд:

```bash
cp _drafts/article-template.md _posts/2026-07-30-local-first-ai.md
git add _posts/2026-07-30-local-first-ai.md
git commit -m "Добавлена статья о local-first AI"
git push
```

После отправки изменений workflow «Публикация сайта» соберёт сайт. Статья появится по адресу `https://askidmobile.github.io/articles/local-first-ai/`.

## Метаданные статьи

```yaml
---
layout: post
title: "Название статьи"
description: "Короткое описание для главной страницы и поисковых систем."
date: 2026-07-30 12:00:00 +0300
tags: [ai, architecture]
---
```

- `title` — заголовок публикации;
- `description` — краткий анонс;
- `date` — дата и время публикации с часовым поясом;
- `tags` — темы статьи.

Заголовок первого уровня добавляется шаблоном автоматически, поэтому текст статьи лучше начинать со вступления, а разделы — с `##`.

## Изображения

Положите файл в `assets/images/`, затем добавьте в статью:

```markdown
![Описание изображения](/assets/images/file-name.png)
```

Имена файлов лучше писать латиницей, в нижнем регистре и через дефисы.

## Локальный предпросмотр

На macOS лучше использовать Ruby из Homebrew, а не устаревший системный Ruby:

```bash
brew install ruby
"$(brew --prefix ruby)/bin/gem" install bundler
"$(brew --prefix ruby)/bin/bundle" install
"$(brew --prefix ruby)/bin/bundle" exec jekyll serve --livereload
```

Сайт будет доступен по адресу `http://127.0.0.1:4000`.

## Первое включение GitHub Pages

В репозитории откройте **Settings → Pages** и выберите **Source → GitHub Actions**. После этого запустите workflow вручную или отправьте новый коммит в `main`.
