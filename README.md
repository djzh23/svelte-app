# Modern Svelte Task Management App

A basic and modern task management application built with Svelte Framework, for personal use. 

## 🌐 Live Demo
Visit the live application at: [https://mysite.netlify.app/](https://news-zi.netlify.app/)

## ✨ Features

- 🎨 Modern and responsive UI design
- 📝 Task management system
- 📸 Photo gallery
- 🎨 Color picker tool
- ⚡ Fast and lightweight

## 🛠️ Tech Stack

- Svelte 3
- Svelte Materialify
- Rollup
- PostCSS
- SASS

## 🚀 Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/djzh23/svelte-app.git
cd svelte-app

```

2. Install dependencies:
```bash
npm install
```

3. Fix any audit issues:
```bash
npm audit fix
```

4. Update Rollup plugins (if needed):
```bash
npm uninstall rollup-plugin-node-resolve rollup-plugin-commonjs
npm install --save-dev @rollup/plugin-node-resolve @rollup/plugin-commonjs
npm install
```

### Development

To start the development server:

```bash
npm run dev
```

The app will be available at `http://localhost:PORT`

## 📁 Project Structure

```
src/
├── components/
│   ├── layout/      # Layout components
│   ├── features/    # Feature-specific components
│   └── common/      # Reusable components
├── peekComponents/  # Additional components
└── App.svelte       # Main application component
```

## 🚀 Deployment

This project is configured for easy deployment on Netlify. The `netlify.toml` file includes the necessary build settings and redirects.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

