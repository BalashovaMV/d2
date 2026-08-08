# Задачи и следующие действия

## P0 — обязательно до рекомендации

### T1. Post-fix независимый аудит

- Перезапустить `analysis/agent_fantasy/recompute_fantasy.py` дважды.
- Проверить `fmean`, gapfilled input, five-series stable/upside, conditional sixth.
- Сверить хэши с `analysis/agent_fantasy/run_metadata.json`.
- Проверить, что прежний verdict критика B1 про `sum` явно отозван первичным клиентом.
- Deliverable: `analysis/postfix_audit/report.md` со статусом READY/NOT READY.

### T2. Consensus двух моделей

- Заморозить правило ensemble до просмотра удобного победителя.
- Рекомендуемый вариант: larger-sample shrinkage для среднего + series-tail bootstrap для p20/p95.
- Провести leave-one-event-out sensitivity.
- Показать rank interval, а не только точечное место.

### T3. Exact reroll stop-rule

- Вход: `analysis/current_fantasy_state.json`.
- Последний экран: Core выбран; 6 жетонов; действия:
  1. заменить показатели красных эмблем;
  2. заменить показатель случайной зелёной эмблемы;
  3. заменить свойства красных эмблем.
- Сравнить expected value, downside и вероятность целевого Teamfight при сохранении качества 290%.
- Разделить stable и upside рекомендацию.
- После каждого фактического клика требовать новый скриншот.

### T4. Итоговый отчёт

- Свести команды, игроков, эмблемы, title, Swiss и uncertainty.
- Маркировать источники: official / client primary / data API / secondary / community.
- Не обещать percentile как гарантию.

## P1 — обязательная упаковка

### T5. Обновить status

Заменить устаревший `analysis/ti_2026_research_status.md` актуальной матрицей.

### T6. Final snapshot

Запустить `analysis/scripts/create_project_snapshot.ps1` после всех исправлений; проверить все hashes; сохранить отдельный final ZIP.

## P2 — после появления внешних данных

### T7. Настоящая стартовая сетка Swiss

- Проверить официальные группы/R1.
- Заменить scenario priors на опубликованные пары.
- Перезапустить 100 000 simulations и обновить вероятности.

## P3 — необязательное углубление

### T8. OpenDota detail coverage

- Resume script: `analysis/data_gap_rules/audit_replay_coverage.py`.
- Machine checkpoint: `analysis/data_gap_rules/handoff_checkpoint.json`.
- Это защищает от overclaim и углубляет drafts/timelines, но не блокирует Fantasy.
- Не скачивать весь `.dem` corpus без отдельного storage plan.

