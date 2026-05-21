# MCGA — Make Commits Great Again

Claude Code-скиллы, которые превращают обычные git-коммиты в драматичные твиты в стиле Дональда Трампа. КАПС. Восклицания. Самовосхваление.

> Лучшие скиллы для коммитов в истории. Поверьте мне.

В репо две версии — выбирай язык:

| Скилл | Язык | Куда смотреть |
|---|---|---|
| [`MCGA/`](./MCGA/) | 🇷🇺 Русский | КАТАСТРОФА, ИСПРАВЛЕНО, ВЕЛИКО, ПЕЧАЛЬНО! |
| [`MCGA-EN/`](./MCGA-EN/) | 🇬🇧 English | DISASTER, FIXED, HUGE, SAD! |

Стиль один — пафос, рубленые фразы, обвинение прошлого, финальная эмоция отдельной строкой. Меняется только язык.

---

## Пример

**Было:**

```
fix: исправил утечку токенов в auth-middleware
```

**Стало (RU):**

```
fix: КАТАСТРОФА в auth — ИСПРАВЛЕНО!

JWT-токены УТЕКАЛИ годами. Прошлая команда ЗНАЛА. Молчала.
Мы пришли. Посмотрели. ИСПРАВИЛИ. Лучший фикс в истории.

ПЕЧАЛЬНО, что это так долго!
```

**Стало (EN):**

```
fix: DISASTER in auth — FIXED!

JWT tokens were LEAKING for years. Previous team KNEW. Said nothing.
We came in. We looked. We FIXED it. Best fix in history.

SAD that it took so long!
```

---

## Установка

Skills в Claude Code лежат в одной из двух директорий:

| Уровень | Путь |
|---|---|
| Пользовательский | `~/.claude/skills/<name>/` |
| Проектный | `<repo>/.claude/skills/<name>/` |

Склонируй репо один раз и скопируй нужную подпапку:

```bash
git clone https://github.com/MowoGroup/MCGA.git /tmp/mcga-skills

# русская версия — глобально
cp -r /tmp/mcga-skills/MCGA ~/.claude/skills/MCGA

# английская версия — глобально
cp -r /tmp/mcga-skills/MCGA-EN ~/.claude/skills/MCGA-EN
```

Можно ставить обе — они активируются разными триггерами (`MCGA` против `/mcga-en`, «коммит в стиле Трампа» против «Trump-style commit») и не конфликтуют.

Подробности и проверка установки — в README каждой версии:
- [`MCGA/README.md`](./MCGA/README.md)
- [`MCGA-EN/README.md`](./MCGA-EN/README.md)

---

## Структура репо

```
MCGA/
├── MCGA/         # русская версия скилла
│   ├── SKILL.md
│   └── README.md
├── MCGA-EN/      # английская версия скилла
│   ├── SKILL.md
│   └── README.md
├── LICENSE       # MIT, общий для обеих версий
└── README.md     # этот файл
```

---

## Лицензия

[MIT](./LICENSE) © 2026 Mowo Group
