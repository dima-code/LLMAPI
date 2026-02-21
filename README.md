# LLMAPI

Vapor API для анализа состава косметики (BotHub / GPT). Используется мобильным приложением Purely.

## Локальный запуск

```bash
# Ключ BotHub (опционально, иначе используется плейсхолдер)
export BOTHUB_API_KEY="твой_ключ"

swift build
swift run Run
```

Проверка: http://localhost:8080/testt → `Ok`.

## Деплой на Railway

1. Создай **новый репозиторий** на GitHub и запушь сюда только содержимое папки `api` (корень репо = эта папка с `Package.swift`, `Dockerfile`, `LLMAPI/`).
2. На [railway.app](https://railway.app): **New Project** → **Deploy from GitHub repo** → выбери этот репозиторий.
3. В настройках сервиса: **Networking** → **Generate Domain**.
4. В **Variables** добавь `BOTHUB_API_KEY` с ключом от bothub.chat.

Эндпоинт для приложения: `https://твой-домен.up.railway.app/analyze` (POST, body: `{"text": "..."}`).
