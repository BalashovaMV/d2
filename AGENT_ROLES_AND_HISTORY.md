# Агенты: роли, история и результат

## Основная ветка `/root`

Интеграция данных, модели, коммуникация с пользователем, snapshot и handoff. Должна принять окончательное решение только после post-fix проверки.

## `ti_teams_form` / Popper

Статус: завершён.

Результат: независимый аудит 16 команд, 1 102 series rows, 2 321 team-map rows, формы/Tier-1/SOS/roster transitions. Главный файл: `analysis/agent_teams/report.md`.

## `fantasy_players` / Sartre

Статус: оборван инфраструктурным `403`, но оставил исходный код и промежуточные рейтинги в `analysis/agent_fantasy/`.

Его работу заменил `fantasy_code_fixes`.

## `final_critic` / Bacon и `critic_recovery`

Статус: итоговый audit сохранён в `analysis/agent_critic/report.md`.

Полезно нашёл: unconditional sixth series, 49 gaps, mutable inputs, false exact-current labels, FISSURE mismatch, Swiss labels/priors и replay overclaim.

Важно: его B1 про необходимость суммировать Core/Support оказался неверен. Первичный клиент Dota 2 доказал `fmean`; этот пункт отозван.

## `fantasy_code_fixes`

Статус: завершён.

Закрыл gapfilled input, five-series stable/upside, conditional sixth, empirical Game3, frozen inputs, reproducible hashes. Главный файл: `analysis/fixes_fantasy/report.md`.

## `data_gap_rules`

Статус основной задачи: завершён; необязательный API coverage безопасно остановлен и полностью возобновляем.

Закрыл 49/49 OpenDota gaps; извлёк текущие правила/коэффициенты из Dota build 24503204; сохранил hashes, paths и line extracts; отделил OpenDota detail JSON от literal `.dem`. Углублённый detail-ledger остановлен на 1 064/1 591 карт (66.8762%), остаётся 527 необязательных карт. Главные файлы: `analysis/data_gap_rules/report.md` и `analysis/data_gap_rules/handoff_checkpoint.json`.

## `roster_swiss_fixes`

Статус основной задачи: завершён на 100% в пределах доступных данных.

Проверил составы через player IDs; отделил 191 карту с другой пятёркой; унифицировал FISSURE semantics; исправил sparse priors и Swiss labels. Контрольные суммы: 1 364 exact-five + 191 карта со стендином/другой пятёркой + 0 непроверяемых = 1 555 post-change team-map views. Swiss Main Event probability sum = 800%; FISSURE sensitivity содержит 48 строк, максимальный сдвиг ранга 2. Главные файлы: `analysis/roster_swiss_fixes/report.md` и `analysis/roster_swiss_fixes/handoff_checkpoint.json`.

## Ветки `mechanics_recovery` и ранние recovery

Статус: инфраструктурный `403`; не являются источником финальных данных. Их задача заменена `data_gap_rules` и первичным клиентским evidence.

## Почему были 403

Запросы подагентов к `chatgpt.com/backend-api/codex/responses` блокировались Cloudflare. Это не отсутствие пользовательских разрешений и не ошибка Dota/OpenDota. Сохранённые на диске файлы выжили; работу продолжали новыми или основной веткой.
