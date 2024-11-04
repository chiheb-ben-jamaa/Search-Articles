# Vue 3 Text Search Application

A modular Vue 3 application built with TypeScript that implements real-time text search functionality.
The application allows users to search through articles with highlighted results and displays matching content dynamically.

## Features

- Real-time search as you type
- Highlighted search results
- Result count display
- Modular component architecture
- TypeScript support
- Responsive design

## Project Structure

```
src/
├── components/
│   ├── SearchInput.vue    # Search input field component
│   ├── SearchResults.vue  # Results list container
│   └── SearchResultItem.vue # Individual result item
├── types/
│   └── Article.ts         # TypeScript interfaces
├── data/
│   └── articles.ts        # Sample article data
└── App.vue               # Root component
```

## Prerequisites

- Node.js (version 14 or higher)
- npm or yarn

## Setup Instructions

1. Clone the repository:

```bash
git clone [repository-url]
```

2. Navigate to the project directory:

```bash
cd Search-Articles
```

3. Install dependencies:

```bash
npm install
```

4. Start the development server:

```bash
npm run dev
```

5. Open your browser and visit the local server URL provided by Vite

## Development

- The application uses Vue 3's Composition API with `<script setup>` syntax
- Components are modular and reusable
- TypeScript is used for type safety
- Styling is component-scoped for better maintainability

## Building for Production

To create a production build:

```bash
npm run build
```

The built files will be in the `dist` directory.

## Preview Production Build

To preview the production build locally:

```bash
npm run preview
```

## Type Checking

Run type checking with:

```bash
vue-tsc
```

## Technologies Used

- Vue 3
- TypeScript
- Vite
- Vue Composition API
