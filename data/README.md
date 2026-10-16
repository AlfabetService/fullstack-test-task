# Данные

100 рецептов и продукты, которые в них встречаются. Названия на английском и румынском.

## `recipes.json`

Массив рецептов:

```json
{
  "id": 265,
  "title": {
    "en": "Oven-roasted chicken with potatoes and vegetables",
    "ro": "Pui la cuptor cu cartofi și legume"
  },
  "servings": 4,
  "ingredients": [
    { "foodId": 145, "amount": 1, "unit": "PC" },
    { "foodId": 113, "amount": 1, "unit": "KG" },
    { "foodId": 96, "amount": 30, "unit": "ML" }
  ]
}
```

- `servings` — на сколько порций рассчитан рецепт целиком.
- `ingredients[].amount` — количество на весь рецепт, не на порцию.
- `ingredients[].foodId` — ссылка на `id` в `foods.json`. У каждого ингредиента продукт есть всегда.
- `ingredients[].unit` — единица измерения, одно из значений:

| Код      | Значение                             |
| -------- | ------------------------------------ |
| `G`      | грамм                                |
| `KG`     | килограмм                            |
| `ML`     | миллилитр                            |
| `L`      | литр                                 |
| `PC`     | штука (яйцо, луковица, целая курица) |
| `CLOVES` | зубчик (чеснок)                      |
| `SLICES` | ломтик (лимон, хлеб)                 |

## `foods.json`

Массив продуктов:

```json
{ "id": 1, "nameEN": "milk", "nameRO": "lapte", "category": "Dairy & Eggs" }
```

Продукт общий для всех рецептов, где он встречается: «eggs» (`foodId` 111) встречается в 45 рецептах из 100, и это одна
и та же запись. `category` — редакционная категория каталога, не связана с USDA.
