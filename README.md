# AIHCG — AI Health Care Guide

<div align="center">

[![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-3178C6?logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-06B6D4?logo=tailwindcss)](https://tailwindcss.com/)
[![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?logo=vercel)](https://vercel.com/)

**An AI-powered health care guide that delivers personalized health insights, recommendations, and guidance through an intelligent conversational interface.**

</div>

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Available Scripts](#-available-scripts)
- [UI Components](#-ui-components)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🩺 About the Project

**AIHCG** (AI Health Care Guide) is a modern, full-stack web application that leverages the power of large language models to provide users with personalized health care guidance. Built with cutting-edge technologies including **Next.js 16**, **React 19**, and the **Vercel AI SDK**, AIHCG offers an intuitive and responsive interface for users to explore health topics, receive AI-generated health recommendations, and track wellness insights — all in one place.

> ⚠️ **Disclaimer**: AIHCG is intended for informational purposes only. It is not a substitute for professional medical advice, diagnosis, or treatment. Always seek the guidance of a qualified health provider with any questions you may have regarding a medical condition.

---

## ✨ Features

- 🤖 **AI-Powered Conversations** — Engage with an intelligent AI assistant powered by the Vercel AI SDK to get health-related information and guidance.
- 📊 **Interactive Health Dashboard** — Visualize health metrics and trends through rich, interactive charts built with Recharts.
- 🎨 **Modern UI Components** — A comprehensive, accessible component library powered by shadcn/ui and Radix UI primitives.
- 🌙 **Dark / Light Mode** — Seamless theme switching with `next-themes` for comfortable viewing in any environment.
- 📱 **Fully Responsive** — Mobile-first design using Tailwind CSS v4 that looks great on any device.
- ⚡ **Smooth Animations** — Polished micro-interactions and transitions powered by Framer Motion.
- 📅 **Date & Calendar Tools** — Integrated date pickers and calendar components for scheduling and tracking health appointments.
- 📋 **Form Validation** — Robust form handling with React Hook Form and type-safe schema validation via Zod.
- 🔔 **Toast Notifications** — Non-intrusive feedback messages with Sonner.
- 📈 **Vercel Analytics** — Built-in usage analytics via `@vercel/analytics`.
- 🔐 **Type-Safe Codebase** — End-to-end TypeScript for reliability and maintainability.

---

## 🛠 Tech Stack

### Core Framework

| Technology | Version | Purpose |
|---|---|---|
| [Next.js](https://nextjs.org/) | 16.x | Full-stack React framework (App Router) |
| [React](https://reactjs.org/) | 19.x | UI rendering library |
| [TypeScript](https://www.typescriptlang.org/) | 5.7 | Static typing |

### AI & Backend

| Technology | Version | Purpose |
|---|---|---|
| [Vercel AI SDK](https://sdk.vercel.ai/) (`ai`) | 6.x | AI model integration & streaming |
| [`@ai-sdk/react`](https://sdk.vercel.ai/docs/ai-sdk-ui) | 3.x | React hooks for AI interactions |

### Styling

| Technology | Version | Purpose |
|---|---|---|
| [Tailwind CSS](https://tailwindcss.com/) | 4.x | Utility-first CSS framework |
| [tw-animate-css](https://www.npmjs.com/package/tw-animate-css) | 1.3.x | Animation utilities for Tailwind |
| [Framer Motion](https://www.framer.com/motion/) | 11.x | Advanced animations & transitions |

### UI Components

| Technology | Version | Purpose |
|---|---|---|
| [shadcn/ui](https://ui.shadcn.com/) | — | Pre-built, accessible component system |
| [Radix UI](https://www.radix-ui.com/) | Various | Headless, accessible component primitives |
| [Lucide React](https://lucide.dev/) | 0.564.x | SVG icon library |
| [cmdk](https://cmdk.paco.me/) | 1.1.x | Command palette component |
| [Vaul](https://vaul.emilkowal.ski/) | 1.x | Drawer component |
| [Sonner](https://sonner.emilkowal.ski/) | 1.x | Toast notification system |
| [Embla Carousel](https://www.embla-carousel.com/) | 8.x | Touch-friendly carousel |

### Data & Forms

| Technology | Version | Purpose |
|---|---|---|
| [Recharts](https://recharts.org/) | 2.x | Composable charting library |
| [React Hook Form](https://react-hook-form.com/) | 7.x | Performant form state management |
| [Zod](https://zod.dev/) | 3.x | TypeScript-first schema validation |
| [date-fns](https://date-fns.org/) | 4.x | Date utility library |
| [React Day Picker](https://react-day-picker.js.org/) | 9.x | Date picker component |

### Analytics & Deployment

| Technology | Version | Purpose |
|---|---|---|
| [@vercel/analytics](https://vercel.com/analytics) | 1.6.x | Web analytics |
| [Vercel](https://vercel.com/) | — | Hosting & deployment platform |

---

## 📁 Project Structure

```
AIHCG/
├── app/                        # Next.js App Router
│   ├── layout.tsx              # Root layout (fonts, theme, analytics)
│   ├── page.tsx                # Home page
│   ├── globals.css             # Global styles & Tailwind CSS
│   └── api/                    # API Route handlers
│       └── chat/               # AI chat endpoint
│           └── route.ts
├── components/                 # Reusable React components
│   ├── ui/                     # shadcn/ui base components
│   │   ├── button.tsx
│   │   ├── card.tsx
│   │   ├── dialog.tsx
│   │   ├── input.tsx
│   │   └── ...
│   └── ...                     # Feature-specific components
├── lib/                        # Shared utilities
│   └── utils.ts                # Helper functions (e.g., `cn` utility)
├── hooks/                      # Custom React hooks
├── public/                     # Static assets (images, icons)
├── components.json             # shadcn/ui configuration
├── next.config.mjs             # Next.js configuration
├── package.json                # Project dependencies & scripts
├── postcss.config.mjs          # PostCSS / Tailwind configuration
├── tailwind.config.ts          # Tailwind CSS configuration
└── tsconfig.json               # TypeScript configuration
```

---

## 📦 Prerequisites

Before running this project locally, make sure you have the following installed:

- **Node.js** ≥ 18.x — [Download](https://nodejs.org/)
- **pnpm** ≥ 8.x — [Install](https://pnpm.io/installation)

  ```bash
  npm install -g pnpm
  ```

- An **AI provider API key** (e.g., OpenAI, Anthropic, Google Gemini, etc.) compatible with the Vercel AI SDK.

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/kuldeep0291-hub/AIHCG.git
cd AIHCG
```

### 2. Install Dependencies

```bash
pnpm install
```

### 3. Set Up Environment Variables

Copy the example environment file and fill in your credentials:

```bash
cp .env.example .env.local
```

Then edit `.env.local` with your API keys (see [Environment Variables](#-environment-variables) below).

### 4. Run the Development Server

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to view the app.

---

## 🔐 Environment Variables

Create a `.env.local` file in the root directory and configure the following variables:

```env
# AI Provider API Key (required)
# Replace with your chosen provider's key:
# OpenAI:    OPENAI_API_KEY=sk-...
# Anthropic: ANTHROPIC_API_KEY=sk-ant-...
# Google:    GOOGLE_GENERATIVE_AI_API_KEY=AIza...
OPENAI_API_KEY=your_api_key_here

# Base URL (optional, for self-hosted or custom AI endpoints)
# AI_BASE_URL=https://api.openai.com/v1
```

> 💡 **Tip**: The Vercel AI SDK supports many providers out of the box. Visit the [AI SDK Providers documentation](https://sdk.vercel.ai/providers/ai-sdk-providers) for the full list of supported models and providers.

---

## 📜 Available Scripts

All scripts are run using `pnpm`:

| Script | Command | Description |
|---|---|---|
| `dev` | `pnpm dev` | Start the Next.js development server with hot reload |
| `build` | `pnpm build` | Build the application for production |
| `start` | `pnpm start` | Start the production server (after `build`) |
| `lint` | `pnpm lint` | Run ESLint to check for code issues |

---

## 🧩 UI Components

AIHCG uses [shadcn/ui](https://ui.shadcn.com/) (New York style) built on top of [Radix UI](https://www.radix-ui.com/) primitives. The full set of installed components includes:

<details>
<summary>View all installed components</summary>

- **Accordion** — Collapsible content sections
- **Alert Dialog** — Modal confirmation dialogs
- **Aspect Ratio** — Maintain responsive aspect ratios
- **Avatar** — User profile images with fallbacks
- **Checkbox** — Accessible checkbox inputs
- **Collapsible** — Show/hide content sections
- **Command** (`cmdk`) — Keyboard-first command palette
- **Context Menu** — Right-click context menus
- **Dialog** — Accessible modal windows
- **Dropdown Menu** — Floating dropdown menus
- **Hover Card** — Hover-triggered information cards
- **Input OTP** — One-time password input
- **Label** — Accessible form labels
- **Menubar** — Horizontal application menus
- **Navigation Menu** — Site navigation menus
- **Popover** — Floating content panels
- **Progress** — Progress bar indicator
- **Radio Group** — Mutually exclusive option selection
- **Resizable Panels** — Adjustable split-pane layouts
- **Scroll Area** — Custom scrollbars
- **Select** — Accessible select dropdowns
- **Separator** — Visual content dividers
- **Slider** — Range input sliders
- **Switch** — Toggle switches
- **Tabs** — Tabbed content navigation
- **Toast** / **Sonner** — Notification toasts
- **Toggle** / **Toggle Group** — Press-to-activate buttons
- **Tooltip** — Hover tooltips
- **Vaul Drawer** — Mobile-friendly slide-up drawers

</details>

To add additional shadcn/ui components, use:

```bash
pnpx shadcn@latest add <component-name>
```

---

## 🌐 Deployment

### Deploy to Vercel (Recommended)

The easiest way to deploy AIHCG is with [Vercel](https://vercel.com/), the platform built by the creators of Next.js.

1. Push your repository to GitHub.
2. Visit [vercel.com/new](https://vercel.com/new) and import your repository.
3. Add your [Environment Variables](#-environment-variables) in the Vercel project settings.
4. Click **Deploy**.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/kuldeep0291-hub/AIHCG)

### Manual / Self-Hosted Deployment

```bash
# Build the production bundle
pnpm build

# Start the production server
pnpm start
```

The server will start on port `3000` by default. You can change the port with:

```bash
pnpm start -p 8080
```

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

1. **Fork** the repository.
2. **Create** a new feature branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Commit** your changes with a descriptive message:
   ```bash
   git commit -m "feat: add your feature description"
   ```
4. **Push** to your branch:
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Open** a Pull Request against the `main` branch.

### Code Style

- Follow the existing TypeScript and React conventions.
- Run `pnpm lint` before submitting a PR to ensure there are no linting errors.
- Keep components small, focused, and reusable.

---

## 📄 License

This project is licensed under the **MIT License**.

---

<div align="center">

Made with ❤️ using [Next.js](https://nextjs.org/), [Vercel AI SDK](https://sdk.vercel.ai/), and [shadcn/ui](https://ui.shadcn.com/)

</div>