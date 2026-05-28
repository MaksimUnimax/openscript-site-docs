# Course Lesson Map

Working title:

**Как разрабатывать с помощью ChatGPT и Codex**

## Lesson 1 — Как теперь можно делать проекты без знания кода

Focus:
User does not need to write code manually, but must understand the process.

## Lesson 2 — Кто что делает: пользователь, ChatGPT и Codex

Focus:
Roles.

## Lesson 3 — Почему проект начинается с документов

Focus:
Documents are project memory.

## Lesson 4 — Как начинать новый диалог после перерыва

Focus:
Restore context first.

## Lesson 5 — Как обновляется документация во время работы

Focus:
Docs update after important decisions/results.

## Lesson 6 — Зачем нужны ТЗ и roadmap

Focus:
TZ says what we build.
Roadmap says in what order.

## Lesson 7 — Git простыми словами

Focus:
Git as history and rollback point.

### Дополнение: как дать Codex право отправлять проект в GitHub

Иногда Codex работает на сервере и должен отправить готовые изменения в GitHub. Для этого серверу нужен доступ к конкретному репозиторию.

Обычный безопасный способ — **deploy key**.

Deploy key — это специальный SSH-ключ, который даёт серверу доступ только к одному репозиторию GitHub. Это лучше, чем давать полный доступ ко всему аккаунту.

Главное правило:

**приватный ключ никогда нельзя копировать в чат, отправлять GPT, вставлять в prompt или показывать кому-либо.**

Правильный безопасный порядок такой:

1. Codex создаёт ключ на сервере.
2. Codex показывает только публичный ключ.
3. Пользователь копирует публичный ключ.
4. Пользователь открывает GitHub-репозиторий.
5. Заходит в `Settings → Deploy keys → Add deploy key`.
6. Вставляет публичный ключ.
7. Включает галочку `Allow write access`, если Codex должен не только читать, но и отправлять изменения.
8. Возвращается в терминал Codex и нажимает Enter.
9. Codex проверяет доступ и делает push.

Важно понимать разницу:

**публичный ключ** можно вставлять в GitHub.  
**приватный ключ** должен оставаться только на сервере.

Пример публичного ключа выглядит примерно так:

`ssh-ed25519 AAAA... openscript-site-docs deploy key`

Если GitHub пишет `Permission denied`, значит ключ не добавлен, добавлен не в тот репозиторий или не включена галочка `Allow write access`.

Главная мысль:

> Deploy key нужен, чтобы Codex мог безопасно отправлять изменения в GitHub, не получая доступ ко всему аккаунту пользователя.

#### Тест к этому блоку

**Вопрос 1. Что можно вставлять в GitHub Deploy keys?**

A. Приватный ключ  
B. Публичный ключ  
C. Пароль от GitHub  
D. Токен от ChatGPT

**Правильный ответ:** B. Публичный ключ.

---

**Вопрос 2. Что нельзя показывать GPT, Codex или вставлять в чат?**

A. Название репозитория  
B. Публичный ключ  
C. Приватный ключ  
D. Ссылку на GitHub-репозиторий

**Правильный ответ:** C. Приватный ключ.

---

**Вопрос 3. Зачем нужна галочка `Allow write access`?**

A. Чтобы Codex мог только читать репозиторий  
B. Чтобы Codex мог отправлять изменения в репозиторий  
C. Чтобы удалить репозиторий  
D. Чтобы открыть сайт в браузере

**Правильный ответ:** B. Чтобы Codex мог отправлять изменения в репозиторий.

---

**Вопрос 4. Что должен сделать Codex после того, как пользователь добавил ключ в GitHub?**

A. Сразу удалить проект  
B. Проверить доступ и выполнить push  
C. Попросить пароль от GitHub  
D. Попросить приватный ключ

**Правильный ответ:** B. Проверить доступ и выполнить push.

#### Главное запомнить

Deploy key — это безопасный способ дать серверу доступ к одному GitHub-репозиторию. Codex может создать ключ и показать публичную часть, а пользователь добавляет её в GitHub. Приватный ключ никогда не показывается и не копируется.

## Lesson 8 — Как идёт один безопасный шаг разработки

Focus:
User -> GPT -> Codex -> report -> GPT -> visual check -> docs update.

## Lesson 9 — Что значит отчёт Codex

Focus:
GPT explains the report; user does not need deep technical parsing.

## Lesson map update 2026-05-28 — Current course status

The lesson map is currently the first structure of the course, not the final student-ready curriculum.

Confirmed course title:

**Как разрабатывать с помощью ChatGPT и Codex**

Confirmed course placement:

inside “Работа с ИИ” after payment.

Confirmed lesson principles:

- no free-writing homework;
- tests with ready answers only;
- no requirement that the user writes Codex prompts manually;
- GPT prepares Codex prompts;
- Codex executes;
- user returns report to GPT;
- GPT explains;
- user checks result visually.

Confirmed Git lesson addition:

Lesson 7 includes deploy-key explanation:
- Codex creates a key on the server;
- Codex prints only the public key;
- user adds public key to GitHub Deploy keys;
- user enables Allow write access if push is needed;
- private key must never be copied into chat;
- Codex tests access and pushes.

Next required refinement:
For each lesson, add:
- goal;
- simple explanation;
- visual idea;
- 3–5 test questions;
- correct answers;
- “Главное запомнить”.
