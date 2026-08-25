# NextShop — eCommerce Website

NextStore is a modern, responsive eCommerce frontend built with **React** and **Vite**. It presents a full storefront experience: homepage merchandising, product browsing, product details, and a shopping cart drawer.

The UI is styled with **Tailwind CSS** and **Material Tailwind**, and product/blog data is loaded from a remote REST API through **Redux Toolkit Query**.

---

## Features

- Responsive storefront layout (header, main content, footer)
- Homepage sections: banner, services, categories, featured products, showcase, special products, popular products, brands, and blogs
- Shop page and product details page
- Cart drawer (currently shows an empty-cart state)
- Product countdown timer for special/deals products
- Swiper carousels for banners, products, categories, and blogs
- Lazy-loaded images
- Multi-language and currency selectors in the header (UI)
- RTK Query integration with a live backend API

---

## Tech Stack

| Area | Tools |
| --- | --- |
| Framework | React 18 |
| Bundler | Vite 5 |
| Routing | React Router DOM 6 |
| State / API | Redux Toolkit + RTK Query |
| Styling | Tailwind CSS, Material Tailwind, PostCSS |
| UI extras | Swiper, Heroicons, React Icons, React Hot Toast |
| Other | Moment.js, Lodash, React Helmet, React Lazy Load Image |

---

## Project Structure

```text
nextshop-website-v1/
├── public/                  # Static public assets
├── src/
│   ├── app/                 # Redux store
│   ├── assets/
│   │   ├── data/            # Static nav, footer, product, blog data
│   │   └── images/          # SVG and image assets
│   ├── components/
│   │   ├── AllSections/     # Homepage section components
│   │   ├── Footer/          # Footer (top, middle, bottom)
│   │   ├── Header/          # Header (top, middle, bottom nav)
│   │   └── Shared/          # Reusable UI (cards, carousels, cart, etc.)
│   ├── layouts/             # Main layout (Header + Outlet + Footer)
│   ├── pages/
│   │   ├── Home/
│   │   ├── Shop/
│   │   └── ProductDetails/
│   ├── redux/
│   │   ├── api/             # RTK Query base API
│   │   └── services/        # Products and blogs API services
│   ├── routes/              # App router
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── index.html
├── package.json
├── tailwind.config.js
└── vite.config.js
```

---

## Pages and Routes

| Route | Page | Description |
| --- | --- | --- |
| `/` | Home | Full homepage with all storefront sections |
| `/shop` | Shop | Shop listing page (placeholder UI) |
| `/product-details/:id` | Product Details | Single product fetched by ID from the API |
| `*` | 404 | Fallback for unknown routes |

---

## API

The frontend talks to:

```text
https://nextstore-server.onrender.com/api/v1
```

| Method | Endpoint | Purpose |
| --- | --- | --- |
| GET | `/product/get-all` | Fetch all products |
| GET | `/product/get-product-by-id/:id` | Fetch a single product |
| GET | `/blog/get-all` | Fetch all blogs |

API services live in:

- `src/redux/services/products/productsService.js`
- `src/redux/services/blogs/blogsService.js`

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or later recommended)
- npm (comes with Node.js)

### Installation

```bash
# clone the repository
git clone <repository-url>
cd nextshop-website-v1

# install dependencies
npm install
```

### Run locally

```bash
npm run dev
```

The app starts on the Vite default URL, usually `http://localhost:5173`.

### Production build

```bash
npm run build
```

Preview the production build:

```bash
npm run preview
```

### Lint

```bash
npm run lint
```

---

## Design Tokens

Custom brand colors are defined in `tailwind.config.js`:

| Token | Hex | Usage |
| --- | --- | --- |
| `primary` | `#3185fc` | Main accent / links |
| `secondary` | `#eb3b5a` | Highlights / sale |
| `tertiary` | `#f48c06` | Extra accent |
| `dark-special` | `#102e4a` | Header / dark surfaces |
| `gray-special` | `#f5f5f7` | Section backgrounds |

Fonts: **Open Sans**, **Poppins**, and **Raleway**.

A shared layout class `.ns_container` in `src/index.css` handles page max-width and padding.

---

## Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the development server |
| `npm run build` | Create a production build |
| `npm run preview` | Preview the production build |
| `npm run lint` | Run ESLint on JS/JSX files |

---

## Notes

- The **Shop** page currently renders a placeholder. Product listing is fully implemented on the Home page via API-backed sections.
- The **Cart drawer** is wired in the header but shows an empty-cart message; cart state is not persisted yet.
- Some header/footer links (account, wishlist, language, currency) are UI-only and do not have dedicated pages yet.

---

## License

This project is private (`"private": true` in `package.json`).
