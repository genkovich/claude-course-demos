# claude-course-demos

Monorepo з демо-проектами до курсу **Agentic Engineering з Claude**. Для кожної лекції — окрема підпапка з робочим кодом, промптами і артефактами зі скринкастів.

## Зміст

| Підпапка | Лекція | Що показує |
|---|---|---|
| [`4.1-prompts/`](./4.1-prompts) | 4.1 Як писати промпти | Refactor, few-shot, race condition, verification — мінімальні приклади на TS і Go |
| [`4.8-bc/`](./4.8-bc) | 4.8 Bounded Contexts | Один e-commerce домен на 3 мовах (Go / TS / Py) × 3 рівнях зрілості (flat / feature-first / hexagonal). 9 робочих проектів, arch-test у CI, скринкасти 1–6 |

## Як використовувати

Клонуєш репо один раз:
```bash
git clone https://github.com/genkovich/claude-course-demos
cd claude-course-demos
```

Далі заходиш у потрібну папку і слідуєш README цієї лекції.

## Філософія демо

- **Один e-commerce домен наскрізно** в 4.8-bc — щоб видно було, як одна й та сама фіча росте з flat у feature-first у hexagonal. Не 9 різних прикладів, а одне і те саме на 9 проектах
- **Працюючі ендпоінти, не заглушки** — `docker compose up && make smoke` має повертати 200 на всі 6 ендпоінтів у будь-якому з 9 проектів 4.8-bc
- **Arch-test реальний** — у stage-3 кожної мови є інструмент (`go-arch-lint` / `dependency-cruiser` / `import-linter`), який ловить порушення меж і падає у CI
- **Промпти зі скринкастів — окремий файл** — щоб студент міг скопіпастити рівно той промпт, який звучав у відео

## Структура

```
claude-course-demos/
├── README.md            # цей файл
├── .gitignore
├── 4.1-prompts/         # лекція 4.1
└── 4.8-bc/              # лекція 4.8
    ├── README.md        # карта 9 проектів і скринкастів
    ├── screencast-prompts.md
    ├── templates/       # CLAUDE.md / ARCHITECTURE.md / .claude/rules/ шаблони
    ├── go/              # Go 1.26 + chi/v5 + pgx
    ├── ts/              # Node 22 + Fastify + Knex
    └── py/              # Python 3.12 + FastAPI + SQLAlchemy
```

## Курс

Лекції живуть в Obsidian-сховищі автора. Кожна лекція має посилання на свою підпапку в цьому репо.

- Telegram канал з оновленнями курсу: https://t.me/genkovich_kyrylo
