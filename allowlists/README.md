# Filtram — Allowlists

Здесь лежат **allowlist-ы** для каждой категории блок-листов Filtram. Цель —
не пускать в финальный блок-лист конкретные домены которые upstream-источники
(OISD, Hagezi, StevenBlack и т.д.) классифицируют как нежелательные, но на
практике являются легитимными сервисами.

## Как это работает

1. Generator (приватная репа `as-lukin/Filtram`) на каждый билд тянет upstream'ы
   → merge + dedupe → получается _raw_ список для каждой категории
2. Затем из _raw_ **вычитается** соответствующий `allowlists/<category>.txt`
3. Результат пушится в `<category>.txt` / `<category>.hosts.txt` / `<category>.adguard.txt` в корне репы
4. Node-DNS ноды раз в день делают `pihole -g` — подтягивают свежий блок-лист

Allowlist **побеждает** любой upstream-блок. Это единственный способ удалить
false-positive для всех юзеров Filtram одновременно.

## Формат файлов

```
# Комментарии через #
domain.example          — один конкретный домен (exact match)
.example.com            — wildcard: example.com и все поддомены
```

Сортировка не нужна — generator сам сортирует.

## Категории (файлы)

| Файл | Описание |
|---|---|
| `ads.txt` | Для категории ads (реклама) |
| `adult.txt` | Для категории adult (18+) |
| `crypto.txt` | Для категории crypto (майнеры, ICO скамы) |
| `gambling.txt` | Для категории gambling (казино, ставки) |
| `messengers.txt` | Для категории messengers |
| `phishing.txt` | Для категории phishing |
| `social.txt` | Для категории social |
| `tracking.txt` | Для категории tracking |

Если allowlist для категории отсутствует — generator работает без вычитания.

## Как репортить false positive

Открыть [Issue](https://github.com/as-lukin/Filtram-lists/issues/new) с:
- доменом который ошибочно блокируется (`example.com`)
- категорией где он лежит (ads / tracking / …)
- реальным сервисом к которому ведёт (какой сайт/приложение ломается)
- опционально — скриншот или trace

Либо открыть PR напрямую в `allowlists/<category>.txt`.

## Известные кейсы

- **Ozon CDN** (`edge-mmedia-lb.ozone.ru`, `.ozonusercontent.com`) — MaxMind GeoLite2 ошибочно классифицирует подсеть `185.73.192.0/22` как ZA вместо RU. Плюс media-поддомены попадают в upstream ads по имени
- **Yandex Metrica/AdFox** — целенаправленно блокируется в tracking. Из ads whitelisted корень `yandex.ru` чтобы не ломать поиск и карты
- **Wildberries CDN** (`.wbstatic.net`, `.wbasstatic.net`) — legitimate CDN для картинок товаров
