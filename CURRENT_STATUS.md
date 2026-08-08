# Текущий статус на момент передачи

## Завершено

| Блок | Статус | Главная улика |
|---|---:|---|
| 16 команд и шесть месяцев результатов | готово | `analysis/agent_teams/report.md` |
| Дедупликация 1 591 карт | готово | `analysis/agent_teams/audit_raw.json` |
| Составы через player IDs | готово | `analysis/roster_swiss_fixes/roster_map_verification.csv` |
| 49 OpenDota 429 gaps | 49/49 закрыты | `analysis/data_gap_rules/gap_recovery_metadata.json` |
| Правила/коэффициенты из клиента | готово | `analysis/data_gap_rules/client_rules_parsed.json` |
| Frozen Fantasy inputs + SHA | готово | `analysis/data/raw/fantasy_2026-08-01/manifest.json` |
| Исправленная Fantasy модель | готово | `analysis/fixes_fantasy/report.md` |
| FISSURE sensitivity | готово | `analysis/roster_swiss_fixes/fissure_fantasy_sensitivity.csv` |
| 100 000 Swiss simulations | готово как модель | `analysis/swiss_model_report.md` |
| Pre-final snapshot | готово | `snapshots/20260801-074349Z-ti2026-pre-final/` |
| 34 chat screenshots | готово | `handoff/screenshots_manifest.csv` |

## Исправленная Fantasy-модель

- Core/Support aggregation: `fmean`.
- Stable index: p20 пяти гарантированных серий.
- Upside index: p95 тех же пяти серий.
- Условная шестая серия: отдельная смесь с `P(rank 4–13)` из Swiss.
- Game 3: team-shrunk empirical probability; глобально 237/526 = 45.057%.
- Активный snapshot: gapfilled, warnings = 0.
- Два финальных прогона дали одинаковые output hashes.

Результаты:

| Стратегия | Core | Mid | Support | Ключевой percentile |
|---|---|---|---|---:|
| Current | Liquid | 1w | Xtreme | p20 51 258.60 / p95 63 989.50 |
| Stable | Xtreme | BetBoom | LGD | p20 61 048.12 |
| Upside | LGD | Yandex | LGD | p95 80 075.94 |

## Требует завершения

- Независимый post-fix audit после исправлений.
- Ensemble/consensus rule между основной и независимой моделями.
- Точный reroll stop-rule под последние три доступные кнопки и шесть жетонов.
- Единый финальный отчёт и актуальный research status.
- Final snapshot.

## Внешне ожидаемые данные

- Стартовые группы/R1 пары TI 2026 ещё должны быть опубликованы организатором. До этого Swiss выдаёт сценарные вероятности, а не точную сетку.
- Если новый облачный чат запускается позже 2026-08-01, перед финалом необходимо проверить изменения составов, патча, регламента и публикацию пар.

