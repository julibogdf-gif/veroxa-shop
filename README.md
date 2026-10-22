# VEROXA — интернет-магазин

Адаптивный русскоязычный демо-магазин. Каталог, поиск, фильтры, сортировка и корзина работают без серверной части и платных сервисов. Корзина сохраняется в браузере на этом устройстве.

**Опубликованный сайт:** https://zyvanta-intierniet-maghazin--djdjdjdjdjdjdjk.replit.app  
В адресе осталось техническое имя проекта; название магазина в интерфейсе — VEROXA.

## Быстрый запуск

Требуются Node.js 24 или новее и pnpm.

```bash
pnpm install
PORT=5173 BASE_PATH=/ pnpm --filter @workspace/zyvanta run dev
```

Откройте `http://localhost:5173`.

В Windows PowerShell задайте переменные отдельно:

```powershell
$env:PORT = "5173"
$env:BASE_PATH = "/"
pnpm --filter @workspace/zyvanta run dev
```

Проверка типов и production-сборка:

```bash
pnpm --filter @workspace/zyvanta run typecheck
PORT=5173 BASE_PATH=/ pnpm --filter @workspace/zyvanta run build
```

## Возможности магазина

- Демонстрационный каталог товаров с фотографиями, категориями и ценами
- Поиск, фильтр по категориям и сортировка по цене
- Добавление товаров в корзину, изменение количества и подсчёт общей стоимости
- Сохранение корзины в `localStorage`
- Адаптивная вёрстка для мобильных экранов

Заказы и оплата не подключены. Для фотографий товаров используются публичные изображения Pexels, для шрифта — Google Fonts; ключи API не нужны.

## Технологии и зависимости

- **Основной сайт:** React 19, TypeScript 5.9, Vite 7
- **Стили:** Tailwind CSS 4 и CSS
- **Интерфейс:** Lucide React; в пакете также доступны компоненты Radix UI и другие UI-зависимости
- **Инфраструктура сайта:** Wouter, TanStack Query
- **Монорепозиторий:** pnpm workspaces
- **Соседние заготовки в проекте:** API на Express 5, PostgreSQL/Drizzle ORM и библиотеки OpenAPI-клиента. Текущий магазин ими не пользуется.

Прямые зависимости перечислены в `artifacts/zyvanta/package.json` и манифестах остальных пакетов. Точные версии всех зависимостей закреплены в `pnpm-lock.yaml`.

## Структура исходников

- `artifacts/zyvanta/` — сайт VEROXA: HTML-точка входа, React/TypeScript, стили и конфигурация Vite
- `artifacts/api-server/` — общий API-сервер-заготовка
- `artifacts/mockup-sandbox/` — среда предпросмотра интерфейсных компонентов
- `lib/` — общие библиотеки и API-клиент
- `scripts/` — служебные скрипты
- `package.json`, `pnpm-workspace.yaml`, `pnpm-lock.yaml` — workspace и зависимости проекта

## GitHub

Архив содержит исходники и lock-файл, но не содержит историю Git и не создаёт GitHub-репозиторий. После распаковки проект можно импортировать в GitHub Desktop или загрузить в новый репозиторий через Git.

## Будущая сборка для Android и Google Play

В этом архиве находится адаптивный веб-сайт, а не нативное Android-приложение. Android-проект, APK/AAB и публикация в Google Play пока не создавались. Для этого потребуется отдельный мобильный проект, например на Expo/React Native; текущий сайт останется без изменений.
