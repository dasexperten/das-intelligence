# Estate policy — sales-hunter · emailer · presenter

**Owner (2026-07-14):**

## sales-hunter — отдельный скилл

**sales-hunter** — **отдельный** скилл **поиска клиентов** (B2B hunt, discovery, qualify) и связанной коммерческой воронки.  
Он **сам по себе**. Это **не** emailer и **не** presenter.

**Владелец:** Lauda Briana.  
**Запуск:** только если Owner **явно** просит sales-hunter (не для голого «отправь письмо», не XA/GEO daily cron).

## Куда sales-hunter обращается (handoff)

| Нужно | Скилл | Роль |
|---|---|---|
| Презентация / deck | **`das-presenter`** (+ pptx при необходимости) | Сделать презентацию |
| Отправить письмо | **`emailer`** | Единственный mail path; **virtual-staff** / ALLOWED_FROM |
| Персонализированное сообщение B2B | **`personizer`** (и при send снова **emailer**) | Текст / профиль; send ≠ personizer |
| Другие tools | contacts, pricer, benefit-gate, … | По смыслу задачи |

**Отправка письма = только emailer.**  
**Презентация = только presenter (по handoff).**  
sales-hunter **не** «является» mailer и **не** «является» presenter.

## emailer

SSOT: `das-architektura/SKILLS/emailer` (зеркала `SKILLS/emailer/`).  
Любой агент/скилл, которому нужно **отправить** корпоративную почту → emailer.

## Кратко

1. sales-hunter = **поиск клиентов** (отдельный скилл).  
2. Нужна презентация → handoff **presenter**.  
3. Нужно письмо (через virtual-staff и т.д.) → handoff **emailer**.  
4. Никто не использует sales-hunter **как** mailer.

See `HARD_RULES.md` §7 / §7b.
