# ГОСТ 7.1-2003 — CSL-стиль для Typst

CSL-стиль для оформления библиографического списка по **ГОСТ 7.1-2003** в [Typst](https://typst.app). Предназначен для ВКР, дипломных работ и научных статей с нумерацией источников по порядку упоминания в тексте.

> **Примечание.** ГОСТ 7.1-2003 — более старый стандарт, применявшийся до введения ГОСТ Р 7.0.100-2018. Если ваш вуз или журнал не требует явно старый стандарт, рекомендуется использовать стиль для [ГОСТ Р 7.0.100-2018](https://github.com/Arondy/GOST-R-7.0.100-2018-CSL).

## Использование

Скопируйте файл `gost-7-1-2003.csl` в папку проекта и подключите в документе Typst:

```typst
#bibliography("refs.bib", style: "gost-7-1-2003.csl")
```

Для ссылок в тексте:

```typst
Как показано в @barr2021 и @liu2024, атаки типа LotL...
```

## Возможности

- Общее обозначение материала: `[Текст]` / `[Электронный ресурс]` по п. 4.7
- Разделитель областей `. — ` (точка, пробел, длинное тире, пробел) по п. 4.6.1
- Первый автор перед заглавием в формате `Фамилия, И. О.` по п. 5.1.1
- Авторы после косой черты в формате `И. О. Фамилия` + `[и др.]` по п. 5.1.5
- Область доступа для электронных ресурсов: `Режим доступа: URL (дата обращения: ДД.ММ.ГГГГ)` по п. 7.8
- Поддержка книг, журнальных статей, докладов на конференциях, диссертаций, веб-страниц

## Поддерживаемые типы источников

| BibTeX-тип | Что описывает |
|---|---|
| `@article` | Статья в журнале |
| `@inproceedings` | Доклад на конференции |
| `@book` | Книга |
| `@online` | Веб-ресурс, сайт, онлайн-документ |
| `@thesis` | Диссертация, дипломная работа |
| `@misc` | Прочие источники (лучше использовать `@online`) |

## Пример BibTeX-записи

**Статья в журнале:**
```bibtex
@article{liu2024survey,
  title   = {A survey on the evolution of fileless attacks and detection techniques},
  author  = {Side Liu and Guojun Peng and Haitao Zeng and Jianming Fu},
  journal = {Computers \& Security},
  year    = {2024},
  volume  = {137},
  pages   = {103653},
  url     = {https://www.sciencedirect.com/science/article/pii/S016740482300562X},
  urldate = {2026-01-13}
}
```

**Книга:**
```bibtex
@book{hand2023evading,
  title        = {Evading {EDR}: The Definitive Guide to Defeating Endpoint Detection Systems},
  author       = {Hand, Matt},
  year         = {2023},
  publisher    = {No Starch Press},
  address      = {San Francisco},
  pagetotal    = {352}
}
```

**Веб-ресурс:**
```bibtex
@online{lolbas2025project,
  title   = {Living Off the Land Binaries And Scripts},
  author  = {{LOLBAS Project}},
  year    = {2025},
  url     = {https://lolbas-project.github.io/},
  urldate = {2026-03-24}
}
```

## Примечания по BibTeX

- Организации в качестве авторов заключайте в двойные фигурные скобки: `author = {{CISA}}`
- Диапазоны страниц записывайте через двойной дефис: `pages = {1557--1574}`
- Для книг общее количество страниц указывайте в поле `pagetotal`, а не `pages`
- Дата обращения задаётся через поле `urldate` в формате `ГГГГ-ММ-ДД`

## Лицензия

[MIT](LICENSE)
