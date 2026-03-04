 Vue Reactivity Project Feedback
**Student:** Boxer300

This is a soccer gear shop with product listings — the structure is mostly in place and there is even a reactive store set up, but the core cart functionality is broken because `clothes` is not reactive and `addToCart` is commented out. The graded submission is in the `real/` folder.

## Vite CLI – Mastery
`package.json` (in `real/`) correctly includes `vite`, `vue`, and `vue-router` with proper `dev`, `build`, and `preview` scripts.

## Iteration in Vue – Approaching
`v-for` is used with `:key` on both the product listing and the `<ClothesCart>` section. However, the key is bound to `cloth.name` rather than a unique `id`. If any two items had the same name, Vue would have key collisions. Add an `id` field to each item and use it:

```html
<div v-for="cloth in clothes" :key="cloth.id">
```

## Data Binding – Not Yet
The `clothes` array is declared as a plain `const` — it is not wrapped in `ref()`. This means Vue cannot track changes to it:

```js
// Current (not reactive):
const clothes = [{ name: 'Sponge bob cleats', price: 119.99, ... }, ...]

// Fix — wrap in ref():
import { ref } from 'vue'
const clothes = ref([{ name: 'Sponge bob cleats', price: 119.99, ... }, ...])
```

Note: for a static display-only list this technically renders fine, but if you ever add/remove items the UI will not update.

## Click Methods – Not Yet
The Buy button has an empty `@click` handler:

```html
<button @click="">Buy ME</button>
```

And the `addToCart` function is commented out in the script:

```js
/* function addToCart(clothes){
  console.log(clothes)
  cartSection.cart.append(clothes)  // Note: .append() is a DOM method — use .push() instead
} */
```

You need to uncomment and fix the function, then connect it to the button:

```html
<button @click="addToCart(cloth)">Buy ME</button>
```

```js
function addToCart(cloth) {
  cartSection.cart.push(cloth)
}
```

## Reactive UI – Not Yet
Because `clothes` is not reactive and `addToCart` is commented out, no UI updates happen when the user interacts with the shop. The `cartSection` reactive store from `stores/cart.js` is imported but never used. Once you uncomment and fix `addToCart` to push to `cartSection.cart`, the store will update — but you will also need to display `cartSection.cart` in the template so the user can see their cart.

## Semantic HTML – Approaching
Products are displayed inside plain `<div>` elements. Since these represent individual items for sale, consider using `<article>` tags. Headings (`<h1>` for the shop title, `<h2>` for product details) are used, though using `<h2>` for price, brand, and alt text is not semantically appropriate — those should be `<p>` tags.

```html
<!-- Better: -->
<article v-for="cloth in clothes" :key="cloth.id">
  <h2>{{ cloth.name }}</h2>
  <p>Price: ${{ cloth.price }}</p>
  <p>Brand: {{ cloth.brand }}</p>
  <img :src="cloth.img" :alt="cloth.alt">
  <button @click="addToCart(cloth)">Buy ME</button>
</article>
```

## BEM CSS – Approaching
There are some class names in the stylesheet (`.container`, `.display-card`, `.display-img`) but none follow BEM conventions. These are generic names with no block/element/modifier structure. Apply BEM naming throughout:

```css
/* BEM example: */
.product-card { ... }
.product-card__title { ... }
.product-card__price { ... }
.product-card__button { ... }
.product-card__button--buy { ... }
```

## Bonus – Aesthetics – Approaching
The layout uses flexbox with wrapping on a wheat background — a reasonable start. Adding hover effects on product cards, a visible cart summary panel, and more distinct typography would improve the visual experience.

## Summary of Critical Fixes
1. **Uncomment `addToCart`** and fix the method: use `cartSection.cart.push(cloth)` (not `.append()`).
2. **Connect the button**: change `@click=""` to `@click="addToCart(cloth)"`.
3. **Display the cart** in the template so users can see what they have added — loop over `cartSection.cart`.
4. Wrap `clothes` in `ref()` so the array is reactive for future changes.
5. Use `<p>` tags instead of `<h2>` for price, brand, and alt text — only use heading tags for actual headings.
