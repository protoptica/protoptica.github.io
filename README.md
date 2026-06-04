# Yaroslavna Soldatova — personal site

Одностраничный персональный сайт и CV-артефакты для `Yaroslavna Soldatova`.

## Что лежит в репозитории

- `index.html` — основная страница сайта
- `styles.css` — стили
- `script.js` — анимации появления блоков
- `assets/` — фото и актуальные версии CV
- `scripts/build_cv_docx.py` — генератор `.docx`-версии CV

## CV

Актуальные файлы:

- `assets/Yaroslavna-Soldatova-CV.pdf`
- `assets/Yaroslavna-Soldatova-CV.docx`

Кнопка `Скачать CV` на сайте ведет на PDF из `assets/`.

Публичная версия CV для сайта должна содержать только безопасный набор контактов:

- `email`
- `LinkedIn`

Мобильный номер и другие прямые контакты лучше держать в версии для ручной отправки, а не в публичном `PDF/DOCX`.

## Как пересобрать CV

Из корня проекта:

```bash
/Users/none/.cache/codex-runtimes/codex-primary-runtime/dependencies/python/bin/python3 scripts/build_cv_docx.py
```

После сборки обновится файл:

```text
assets/Yaroslavna-Soldatova-CV.docx
```

## Git

Основная ветка репозитория: `main`.

## Деплой

Сайт публикуется через `GitHub Pages` и workflow:

- `.github/workflows/deploy-pages.yml`

Логика простая:

1. Любой пуш в `main` запускает GitHub Actions.
2. Workflow собирает статический бандл в `dist/`.
3. GitHub Pages публикует содержимое `dist/`.

В публичный бандл попадает только allowlist файлов из `assets/`, а не вся директория целиком.

Если Pages еще не включен в настройках репозитория, нужно один раз выбрать:

- `Settings -> Pages -> Build and deployment -> Source -> GitHub Actions`
