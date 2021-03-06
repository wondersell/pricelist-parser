# Pricelist parser

Библиотека для разбора прайслистов и списков заказов в форматах CSV, XLS и XLSX

### Возможности:

1. Умеет разбирать и вычленять информацию из прайслистов на русском языке.
2. Автоматически определяет структуру прайслиста – где находится строка с названием колонок, где начинаются данные и где они заканчиваются. Не нужно задавать эти параметры вручную
3. Валидирует данные и оставляет только те, которые больше всего похожи на данные из прайслиста. Не нужно волноваться, если менеджер магазина где-то нечаянно добавил лишнюю строку или переусердствовал с форматированием.

### Использование

```
from pricelist_parser import parse_pricelist


parsed_data = parse_pricelist('path/to/pricelist.csv')
```

В ответ вернется массив объектов типа с извленными данными. Каждый объект – один товар из прайслиста или списка заказов. На данный момент объекты содержат поля:

* `sku` – артикул товара (string)
* `price` – цена товара (float)
