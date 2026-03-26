# Data Model (Draft)

Цель: зафиксировать минимальную внутреннюю структуру данных для будущей автоматизации ВК без преждевременного усложнения.

## Статусы
- `CONFIRMED`: напрямую следует из требований пользователя.
- `HYPOTHESIS`: рабочий набросок до анализа реальных входов текущего проекта.

## Ядро (раздел-независимое)
1. `Project` (`HYPOTHESIS`)
- `project_id`
- `project_name`
- `section_code` (например, `VK`, позже `OV1`, `OV2`)

2. `WorkLogEntry` (`CONFIRMED`)
- `log_entry_id`
- `work_type`
- `date_start`
- `date_end`
- `reference_to_source`

3. `Material` (`CONFIRMED`)
- `material_id`
- `material_name`
- `spec_or_mark`
- `unit`
- `quantity`

4. `Certificate` (`CONFIRMED`)
- `certificate_id`
- `certificate_name`
- `certificate_file`
- `material_links[]`

5. `Scheme` (`CONFIRMED`)
- `scheme_id`
- `sheet_or_code`
- `scheme_file`

6. `Act` (`CONFIRMED`)
- `act_id`
- `act_number`
- `act_type`
- `system_code`
- `date_work_end`
- `date_sign`
- `materials[]`
- `certificates[]`
- `schemes[]`
- `has_attachment` (true/false)

7. `Attachment` (`CONFIRMED`)
- `attachment_id`
- `parent_act_id`
- `reason` (например, `certificates_over_5`)
- `items[]`

## Правила связи
- `Act` <- `WorkLogEntry`: для подстановки/проверки дат (`CONFIRMED`).
- `Act` <- `Material` <- `Certificate`: для проверки комплектности (`CONFIRMED`).
- `Act` <- `Scheme`: для ссылок на исполнительные схемы (`CONFIRMED`).

## Минимальные валидации
- акт без номера или типа не считается готовым;
- даты акта не должны конфликтовать с журналом без явной пометки;
- материал без сертификата помечается как риск комплектности;
- если сертификатов на акт 6 и более, требуется приложение.

## Что пока не фиксируем жёстко
- точный набор колонок Word-реестра;
- финальные форматы идентификаторов и кодов систем;
- полный набор типовых актов по ВК.
