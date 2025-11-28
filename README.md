# BookNest

A cozy library catalog and reservation UI built with React.

This repository contains BookNest — a small single-page React app demonstrating a catalog of books, searching and filtering, a reservation/cart flow, reservation confirmation with QR code, and a user dashboard. It includes light and dark themes, responsive layout, and localStorage persistence for user data.

---

## Table of Contents

- Project status
- Screenshots
- Features
- Tech stack
- Getting started (Windows)
- Scripts
- Project structure
- Data source
- Theming & customization
- Contributing
- Known issues
- License

---

## Project status

Status: In development / polishing.

Major flows implemented:
- Browse catalog with search and multi-select genre filters
- Book details with full metadata
- Reservation cart and checkout flow
- Confirmation with unique reservation ID and QR code
- User dashboard with reservations and one-time extension
- Dark mode support and responsive UI

Planned: Final UX polish, lint cleanup, image loading optimizations, and adding tests.

---

## Screenshots

Place screenshots in the repository at `./screenshots/` and reference them below. Example filenames used in this README:

-Home / catalog with filters (Light Mode):
<img width="434" height="802" alt="image" src="https://github.com/user-attachments/assets/0f48c268-ed85-4191-9e42-3510506e1275" />

<img width="433" height="657" alt="image" src="https://github.com/user-attachments/assets/60e75671-4e0f-487a-919f-39c517c274d5" />

-Home / catalog with filters (Dark Mode):
<img width="3072" height="3098" alt="image" src="https://github.com/user-attachments/assets/d1edea65-1770-4452-a49e-0f1e48400618" />


- Book details:
<img width="3072" height="4148" alt="image" src="https://github.com/user-attachments/assets/6188a02e-46d5-4678-89bc-e461bac2dfb4" />

- Reservation Cart:
  <img width="3072" height="2388" alt="image" src="https://github.com/user-attachments/assets/62c2b186-a567-44fd-96fd-a7bc5eb3293e" />

- Empty Reservation Cart:
  <img width="3072" height="1750" alt="image" src="https://github.com/user-attachments/assets/e4305176-2ec6-4421-bd40-f90fb9bfe03e" />

- Reservation Confirmed:
  <img width="3072" height="4448" alt="image" src="https://github.com/user-attachments/assets/8f675867-8438-4769-afc8-1aef1f8e76e1" />

- Checkout:
<img width="3072" height="3162" alt="image" src="https://github.com/user-attachments/assets/b08a5e4c-4d39-4026-b6bb-378c5d40af97" />

- User dashboard:
<img width="3072" height="3098" alt="image" src="https://github.com/user-attachments/assets/17500aae-280e-4ea8-92bf-6d9558d65152" />
  
- Contact Librarian:
<img width="3072" height="3670" alt="image" src="https://github.com/user-attachments/assets/bd6637e4-c5f4-46f3-868c-434e15bea1d1" />



## Features

- Search by title or author (case-insensitive)
- Multi-select genre filters (empty selection = show all)
- Book cards with consistent 3:4 cover aspect ratio
- Copies available badges and availability status
- Add to wishlist (heart icon) — persists to localStorage
- Reservation cart with pickup/due date calculation
- Checkout confirmation page with reservation ID and QR code
- Dashboard with active reservations, history, and one-time extension
- Light and dark themes with CSS variables

---

## Tech stack

- React (Create React App)
- React Router v6
- Context API + useReducer for global state
- Plain CSS modules (in `src/styles/`), CSS variables for theming
- No backend — uses static dataset (`src/data/booksData.js`) and `localStorage` for persistence

---

## Getting started (Windows)

Prerequisites
- Node.js (v16+) and npm

Setup

```powershell
cd 'C:\Users\HP\OneDrive\Desktop\assignment2'
npm install
```

Run the dev server

```powershell
npm start
```

The app will open at `http://localhost:3000` by default.

Build for production

```powershell
npm run build
```

---

## Scripts

- `npm start` — start the dev server
- `npm run build` — build production assets
- `npm test` — runs tests (if present)

---

## Project structure (important files)

- `src/`
  - `App.js` — app root, routing
  - `index.js` — app bootstrap
  - `context/AppContext.js` — global state and persistence
  - `data/booksData.js` — static dataset used by the app
  - `components/` — React components (Home, FeaturedBooks, BookCard, BookDetails, Cart, Checkout, Confirmation, Dashboard)
  - `styles/` — per-component CSS files and `index.css` for variables

- `public/` — static assets, manifest, index.html

---

## Data source

This project uses a curated static JSON-like dataset at `src/data/booksData.js`. Many cover images are loaded from the Open Library Covers API (ISBN-based). If covers are slow to load, see the README section about optimizing images below.

---

## Theming & customization

The app uses CSS variables in `src/index.css` to define the color palette. To customize theme colors, open `src/index.css` and adjust the `:root` variables (for light theme) and `body.dark-mode` overrides (for dark theme).

To toggle dark mode programmatically, the app uses a persisted key in `localStorage` and the `body.dark-mode` class. You can switch by toggling that class in the DOM or using the UI control inside the app.

---


## Troubleshooting

- Navbar import errors (case-sensitive): On Windows this is usually fine, but CI or other OS may be case-sensitive. Ensure component filenames and imports match exactly.
- Slow images: Open Library can be slow; prefer `-M.jpg` covers or add a local fallback. Consider adding `srcSet` or a small blurred placeholder for LQIP.
- LocalStorage: Clear `localStorage` if state gets out of sync during development (keys used: `cart`, `wishlist`, `reservations`, `darkMode`).

---



## Known issues

- Featured images may load slowly from remote sources; consider local caching or smaller image variants.

---

## License

This project is provided as-is for educational/demo use. 

---

# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.




