# ISPOLNIT

Репозиторий для подготовки базы под будущую автоматизацию оформления исполнительной документации по строительному разделу ВК.

## Текущий этап
- Этап: подготовка базы (структура, правила, нормализованная документация).
- Код и пайплайн сейчас не реализуются.
- Текущий алгоритм процесса считается черновым и подлежит регулярному пересмотру.

## Принципы работы
- Не считать исторические заметки финальной спецификацией.
- Не делать молчаливых допущений при нехватке входных данных.
- Явно разделять подтверждённые правила, гипотезы, наблюдения и открытые вопросы.
- Любые противоречия фиксировать в `docs/open-questions.md`.
- Исходные акты из `inputs/` не править по содержимому; в именах разрешено только добавить `№` в начало, если его нет.

## Базовая структура репозитория
```text
.
├── AGENTS.md
├── README.md
├── docs/
│   ├── process-overview.md
│   ├── algorithm-draft.md
│   ├── process-observations.md
│   ├── data-model.md
│   ├── rules-common.md
│   ├── formatting-word.md
│   ├── sources-of-truth.md
│   ├── reference-examples.md
│   ├── open-questions.md
│   ├── next-inputs-checklist.md
│   └── tech-stack-comparison.md
├── sections/
│   └── VK/
│       ├── section-rules.md
│       ├── act-types.md
│       └── field-mapping.md
└── references/
    ├── obsidian/raw/
    └── example-projects/
```

## Где что читать в первую очередь
1. `AGENTS.md`
2. `docs/sources-of-truth.md`
3. `docs/process-overview.md`
4. `sections/VK/*.md`
5. `docs/open-questions.md`
6. `docs/collaboration-pipeline.md`

## Режим совместной работы
- Работа идёт по итерациям с промежуточной проверкой после каждого шага.
- Подробный регламент: `docs/collaboration-pipeline.md`.
