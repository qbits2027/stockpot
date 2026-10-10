# Stockpot

**Plan the week. Shop once.**

Stockpot is a single-page dinner planner. Browse 199 recipes, pick this week's meals, and get one combined shopping list sorted by store aisle, ready to print.

No account, no server, no build step. It's one HTML file that runs in any modern browser.

## Features

- **199 recipes in 9 categories:** Breakfast & Brunch, Soups & Salads, Chicken, Beef & Pork, Seafood (Fish / Other Seafood), Pasta, Vegetarian, Sides and Desserts. Each has servings, total time, ingredients and numbered steps.
- **Combined shopping list:** tick the recipes you want and Stockpot adds up every ingredient across them, converts units (tsp → tbsp → cups, oz → lb, butter in sticks) and rounds whole items up.
- **Sorted by store aisle:** Produce, Meat & Seafood, Dairy, Bread, Grains, Canned, Baking, Spices, Oils & Sauces, Other Items, Frozen, Wine & Spirits. Pantry staples are flagged.
- **Shop from screen or paper:** cross items off as you go, add write-ins, or copy the list as text.
- **Printable Dinner Menu (PDF):** the week's date range, a bulleted "Meals this week", the aisle list with tick boxes and blank lines, then a full recipe card for every meal. Crossed-off items are left off the printout.
- **Favorites:** star recipes and filter the menu to just your favorites.
- **Comfortable to use:** search by recipe or ingredient, collapsible categories, a resizable sidebar, "Uncheck all" with undo, and a layout that works on phones.

Selections, favorites and write-ins are saved in your browser's local storage. Nothing leaves your device.

## Use it

- **Locally:** download `index.html` and open it in your browser.
- **GitHub Pages:** in this repository's *Settings → Pages*, set the source to the `main` branch and the root folder, then open the URL GitHub gives you.

The PDF feature loads [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 (MIT) from cdnjs, and the fonts (Bricolage Grotesque and Figtree) come from Google Fonts. Everything else is inline.

## Customizing

All recipe data lives in the `<script>` block of `index.html`:

- `CATALOG` maps each ingredient to its store aisle.
- `RECIPES` holds the recipes. Each one is `{ id, n: name, c: category, s: serves, t: time, d: description, i: ingredients, st: steps }`. An ingredient is `[quantity, unit, catalogName, note]`, and a quantity of `null` means "to taste".
