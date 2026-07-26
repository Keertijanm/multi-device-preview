# 📱 Multi Device Preview

A modern developer tool for previewing and comparing webpages across multiple devices on a single screen. Perfect for responsive testing, UI validation, and cross-page comparison.

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/Keertijanm/multi-device-preview?style=social)](https://github.com/Keertijanm/multi-device-preview)
[![Built with Next.js](https://img.shields.io/badge/Built_with-Next.js-black?logo=next.js)](https://nextjs.org/)

---

## 📖 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#-initial-tech-stack)
- [Use Cases](#use-cases)
- [Quick Start](#quick-start)
- [Installation](#installation)
- [Development](#development)
- [Project Roadmap](#-project-roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Multi Device Preview is a production-ready web application that helps developers, QA engineers, designers, and website owners test responsive websites faster. Unlike browser DevTools, each preview panel can load a completely different webpage while using different device sizes—making it ideal for UI comparison, regression testing, and responsive validation.

**Key Advantage:** View up to 6 independent preview panels side-by-side, each with its own URL and device configuration.

---

## ✨ Features

- 📱 **Multi-Device Preview** – Display webpages in Mobile, Tablet, and Desktop modes
- 🔀 **Simultaneous Comparison** – Compare multiple webpages side-by-side
- 🎛️ **Independent Configuration** – Each panel has its own URL and device type
- 📐 **Responsive Workspace** – Adaptive layout that works on any screen
- ⚡ **Fast Switching** – Instantly change device types across all panels
- 🎨 **Clean UI** – Intuitive controls for developers and designers
- 🔧 **Developer-Friendly** – Built for developers, by developers

---

## 🚀 Initial Tech Stack

### Frontend
- **Next.js 15** (App Router)
- **React 19**
- **TypeScript** (Strict Mode)

### Styling & UI
- **Tailwind CSS** – Utility-first CSS framework
- **shadcn/ui** – High-quality React components
- **Lucide React Icons** – Beautiful, consistent icons

### Development Tools
- **ESLint** – Code quality and consistency
- **Prettier** – Code formatting
- **pnpm** – Fast, disk space-efficient package manager

### Deployment
- **Vercel** – Optimized for Next.js, zero-config deployment

### Version Control
- **Git** – Distributed version control
- **GitHub** – Repository hosting and collaboration

---

## 🎯 Use Cases

- ✅ **Responsive Website Testing** – Verify layouts across device sizes
- ✅ **UI Validation** – Ensure consistent design implementation
- ✅ **Cross-Page Comparison** – Compare designs across different pages
- ✅ **Design QA** – Validate design handoffs
- ✅ **Client Reviews** – Present multiple designs simultaneously
- ✅ **Website Monitoring** – Track design consistency
- ✅ **Regression Testing** – Detect unintended design changes
- ✅ **Frontend Development** – Speed up development workflow

---

## ⚡ Quick Start

### Prerequisites
- Node.js 18+ 
- pnpm (recommended) or npm

### Installation

```bash
# Clone the repository
git clone https://github.com/Keertijanm/multi-device-preview.git
cd multi-device-preview

# Install dependencies
pnpm install

# Run development server
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🔧 Development

### Available Scripts

```bash
# Development server with hot reload
pnpm dev

# Build for production
pnpm build

# Start production server
pnpm start

# Run ESLint
pnpm lint

# Format code with Prettier
pnpm format
```

### Project Structure

```
multi-device-preview/
├── src/
│   ├── app/                 # Next.js App Router
│   ├── components/          # Reusable React components
│   ├── hooks/              # Custom React hooks
│   ├── utils/              # Utility functions
│   ├── types/              # TypeScript definitions
│   └── styles/             # Global styles
├── public/                 # Static assets
├── docs/                   # Documentation
├── package.json
├── tsconfig.json
├── tailwind.config.js
├── next.config.js
└── README.md
```

### Code Standards

- **TypeScript** – Strict mode enabled
- **ESLint** – Enforce code quality
- **Prettier** – Automatic code formatting
- **Components** – Functional components with React Hooks

---

## 🔮 Project Roadmap

### Phase 1: MVP (Current)
- ✅ Multi-device preview panels
- ✅ URL management
- ✅ Device type switching
- ✅ Responsive layout

### Phase 2: Core Features
- 💾 Save/load workspaces
- 🔗 Synchronized scrolling
- 📸 Screenshot export
- 🌙 Dark mode support

### Phase 3: Advanced Features
- 🔍 Lighthouse integration
- 📊 Performance metrics dashboard
- 🎨 Visual difference highlighting
- 👥 Team sharing & collaboration

### 🔮 Planned Enhancements (Future Versions)

The following technologies are intentionally **NOT** part of the initial MVP and are planned for future versions as the project evolves:

#### Backend & Database
- **PostgreSQL** (via Supabase) – Reliable data storage
- **Prisma ORM** – Type-safe database toolkit
- **Supabase Authentication** – User management

#### Server-Side Features
- **Next.js Server Actions** – Simplified server communication
- **REST APIs** – Robust backend endpoints

#### Testing & Quality Assurance
- **Playwright** – End-to-end testing
- **Vitest** – Unit testing framework
- **React Testing Library** – Component testing

#### CI/CD & Deployment
- **GitHub Actions** – Automated workflows
- **Vercel Analytics** – Performance monitoring

### Development Philosophy

> The first release focuses on delivering a **fast, production-quality frontend experience**. Backend services, authentication, database integration, and advanced collaboration features will be introduced incrementally as the project evolves, based on user feedback and community needs.

---

## 🤝 Contributing

We welcome contributions from the community! 

### How to Contribute

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Make** your changes with clear commit messages
4. **Follow** our [Contributing Guidelines](docs/CONTRIBUTING.md)
5. **Push** to your fork (`git push origin feature/amazing-feature`)
6. **Open** a Pull Request

### Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Follow the existing code style
- Write meaningful commit messages

For detailed guidelines, see [CONTRIBUTING.md](docs/CONTRIBUTING.md).

---

## 📸 Screenshots

*Screenshots coming soon.*

---

## 📝 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 🌍 Part of Web Toolkit

This repository is part of the larger **"Web Toolkit"** ecosystem – a collection of tools for webpage monitoring, comparison, analysis, and responsive testing.

---

## 👨‍💻 Author

Created with ❤️ by [Keerti Gupta](https://github.com/Keertijanm)

---

## 📞 Support & Questions

- 📖 Check the [documentation](docs/)
- 🐛 Found a bug? [Open an issue](https://github.com/Keertijanm/multi-device-preview/issues)
- 💡 Have a feature idea? [Start a discussion](https://github.com/Keertijanm/multi-device-preview/discussions)

---

**Made with ❤️ for developers, designers, and QA engineers.**
