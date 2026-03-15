# Career Guru — AI-Powered Career Guidance Platform

<div align="center">

[![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-3178C6?logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-06B6D4?logo=tailwindcss)](https://tailwindcss.com/)
[![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?logo=vercel)](https://vercel.com/)

**An AI-powered career guidance platform that evaluates whether a student is suited for different career domains — including Research and Business — through a dynamic chatbot interview and a mathematical compatibility scoring model.**

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Supported Career Domains](#-supported-career-domains)
- [Key Features](#-key-features)
- [How Career Guru Works](#-how-career-guru-works)
- [Mathematical Model](#-mathematical-model)
- [Score Normalization Method](#-score-normalization-method)
- [Confidence Model](#-confidence-model)
- [Career Domain Detection](#-career-domain-detection)
- [Alumni Discovery Feature](#-alumni-discovery-feature)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Running Locally](#-running-locally)
- [Future Improvements](#-future-improvements)
- [License](#-license)

---

## 🔍 Overview

**Career Guru** is an AI-powered web application that evaluates whether a student is suited for different career domains — currently **Research** and **Business / Entrepreneurship** — using a dynamic chatbot interview and a mathematical compatibility scoring model. Rather than offering purely conversational advice, the system delivers structured, explainable, and data-driven career guidance backed by a well-defined scoring engine.

Users interact with an adaptive chatbot that conducts a personalised interview. The chatbot dynamically generates follow-up questions using ChatGPT based on previous responses. Once sufficient response consistency is detected, the system computes a compatibility score and automatically identifies the most suitable career domain — no manual selection required.

No sign-up or login is needed to access the platform.

---

## 🎯 Problem Statement

Students pursuing higher education often struggle to determine which career path is the right fit for them — whether that is a research-oriented role or a business / entrepreneurship journey. Existing tools rely on subjective self-assessments or generic advice that lacks rigour. Career Guru addresses this gap by:

- Conducting a structured, adaptive interview to gather meaningful signals about a student's aptitude and motivation.
- Quantifying career compatibility across six measurable dimensions using a weighted nonlinear mathematical model.
- Automatically detecting the most relevant career domain (Research or Business) based on the student's responses.
- Connecting students with real alumni role models who are already working in that field.

---

## 🗂 Supported Career Domains

Career Guru currently evaluates compatibility with two major career domains:

| Domain | Description |
|---|---|
| **Research** | Academic research, scientific investigation, data-driven analysis, publishing, and postgraduate study paths |
| **Business & Entrepreneurship** | Startup founding, product management, market analysis, venture strategy, and commercial innovation |

The system automatically detects the most suitable domain for each user based on their interview responses — no manual selection is required.

---

## ✨ Key Features

- 🔓 **No Sign-Up Required** — Users can access the full platform without creating an account or logging in.
- 🤖 **Dynamic AI Chatbot Interview** — A ChatGPT-powered chatbot conducts a personalised interview that adapts in real time based on previous responses.
- 📐 **Mathematical Compatibility Scoring** — User responses are mapped to numeric values and processed through a weighted nonlinear equation to produce an explainable compatibility score.
- 🧭 **Automatic Career Domain Detection** — The system identifies the most suitable career domain (Research or Business) without requiring manual selection.
- 📊 **Confidence-Based Interview Termination** — The interview continues dynamically until response variance falls below a defined confidence threshold, ensuring result reliability.
- 🎓 **Alumni Discovery** — After evaluation, the platform surfaces recent LinkedIn profiles of alumni from the user's college who are working in the detected career domain.
- 🌙 **Dark / Light Mode** — Seamless theme switching for comfortable viewing in any environment.
- 📱 **Fully Responsive** — Mobile-first design that works across all screen sizes.

---

## ⚙️ How Career Guru Works

1. **Start the Interview** — The user visits the platform (no login required) and begins a chatbot-led interview session.
2. **Adaptive Questioning** — The chatbot generates contextual follow-up questions using ChatGPT, tailoring the conversation based on each previous response.
3. **Response Mapping** — Each answer is mapped to a numeric value in the range **−10 to +10**, covering six evaluation parameters.
4. **Confidence Check** — After each response, the system calculates answer variance. The interview continues until confidence reaches the required threshold.
5. **Score Computation** — The six parameter scores are fed into a weighted nonlinear equation to compute the final compatibility score (ψ), adjusted by a mentality multiplier.
6. **Domain Detection** — The system automatically determines whether the user is best suited for a **Research** or **Business / Entrepreneurship** career domain based on the score profile.
7. **Alumni Showcase** — Relevant LinkedIn profiles of alumni from the user's college working in the detected domain are retrieved and displayed.

---

## 📐 Mathematical Model

### Assessment Parameters

Career Guru measures six key parameters from the chatbot interview:

| Parameter | Symbol | Description |
|---|---|---|
| Interest | `I` | Genuine enthusiasm for the career domain |
| Skill Compatibility | `S` | Alignment between existing skills and career demands |
| Domain Alignment | `D` | Match between preferred domain and career areas |
| Trend Awareness | `T` | Awareness of current trends in the relevant field |
| Growth Awareness | `G` | Understanding of long-term career growth |
| Persistence / Mentality | `P` | Resilience, discipline, and relevant career mindset |

Each parameter is scored in the range **−10 to +10** based on user responses, then normalised to a standard range before being used in the scoring equation.

### Compatibility Score Formula

The raw compatibility score **ψ** is computed using a weighted nonlinear equation:

```
ψ = w₁·I^k₁ + w₂·S^k₂ + w₃·D^k₃ + w₄·T^k₄ + w₅·G^k₅
  + w₆·(I × S) + w₇·(S × T)
```

Where:
- `w₁ … w₇` are tunable **weight coefficients** for each term.
- `k₁ … k₅` are **nonlinear exponents** that amplify or dampen each parameter's contribution.
- The cross-product terms `(I × S)` and `(S × T)` capture **interaction effects** between related parameters.

### Mentality Multiplier Adjustment

The raw score is then adjusted using the Persistence / Mentality parameter as a multiplier:

```
Score = ψ · (1 + α·P)
```

Where:
- `α` is a tunable scaling factor that controls the weight of the mentality adjustment.
- `P` is the normalised Persistence / Mentality score.

This ensures that a student's mindset and resilience amplify or moderate the raw compatibility score.

---

## 📏 Score Normalization Method

Raw response values (−10 to +10) are normalised to a standard range before being used in the compatibility formula. Normalisation ensures that each parameter contributes proportionally and prevents extreme values from dominating the score.

The normalisation formula applied is min-max scaling:

```
x_norm = (x - x_min) / (x_max - x_min)
```

Where:
- `x` is the raw parameter value.
- `x_min = −10` and `x_max = +10` are fixed bounds (the response scale), so `x_max − x_min = 20` is always a nonzero constant.
- `x_norm` falls in the range **[0, 1]**.

---

## 📊 Confidence Model

To ensure the reliability of the compatibility score, Career Guru monitors the **variance** of responses across interview rounds. The chatbot continues asking questions until the responses become sufficiently consistent.

### Variance Formula

```
variance = (1/n) Σ(x − mean)²
```

### Confidence Formula

```
confidence = 1 − (variance / 100)
```

- `variance` is computed across the numeric scores assigned to the user's responses for each parameter.
- The divisor **100** is the theoretical maximum variance for the response scale (the scale spans −10 to +10, giving a range of 20; maximum variance = 10² = 100), so dividing by 100 normalises variance to [0, 1].
- `confidence` therefore falls in the range **[0, 1]**, where 1 indicates perfectly consistent responses and 0 indicates maximum disagreement.
- The interview terminates when `confidence` reaches or exceeds a predefined threshold (e.g., `0.85`).
- This adaptive stopping mechanism prevents premature scoring and ensures that the final result reflects stable, well-considered responses.

---

## 🧭 Career Domain Detection

The user does **not** manually select a career domain. Instead, the system automatically determines the most suitable domain based on patterns detected across the interview.

The two supported domains are evaluated simultaneously, and the domain with the highest compatibility score is recommended.

**Signals used for domain detection:**

| Signal | Research | Business / Entrepreneurship |
|---|---|---|
| Analytical thinking patterns | ✅ Strong indicator | Moderate |
| Risk tolerance | Low preference | ✅ Strong indicator |
| Curiosity and exploration | ✅ Strong indicator | Moderate |
| Problem-solving style | Systematic / experimental | ✅ Strategic / market-driven |
| Decision-making preferences | Evidence-based | ✅ Opportunity-based |

This approach ensures that domain assignment is driven entirely by the student's natural tendencies, not by pre-selected filters.

---

## 🎓 Alumni Discovery Feature

After the compatibility evaluation is complete and the most suitable career domain has been identified, Career Guru surfaces **recent LinkedIn profiles** of alumni from the user's college who are currently working in that domain.

**How it works:**

- The detected career domain (Research or Business) and the user's college name are used to query LinkedIn through a third-party LinkedIn search API (e.g., via RapidAPI or similar providers, as LinkedIn's official API does not expose public profile search for this use case).
- Results are filtered by **college name**, **career domain** (research or business roles), and **recent professional activity** to surface active professionals rather than stale profiles.
- Profiles are displayed on the results page as role model references, giving students concrete examples of career paths they could follow.

> **Note**: Integration with LinkedIn search APIs requires compliance with LinkedIn's Terms of Service and the terms of the chosen third-party provider.

This feature bridges the gap between abstract career scores and real-world inspiration.

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
| [OpenAI / ChatGPT](https://platform.openai.com/) | GPT-3.5-turbo / GPT-4 | Dynamic question generation |

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
| [Sonner](https://sonner.emilkowal.ski/) | 1.x | Toast notification system |

### Data & Forms

| Technology | Version | Purpose |
|---|---|---|
| [Recharts](https://recharts.org/) | 2.x | Composable charting library |
| [React Hook Form](https://react-hook-form.com/) | 7.x | Performant form state management |
| [Zod](https://zod.dev/) | 3.x | TypeScript-first schema validation |

### Analytics & Deployment

| Technology | Version | Purpose |
|---|---|---|
| [@vercel/analytics](https://vercel.com/analytics) | 1.6.x | Web analytics |
| [Vercel](https://vercel.com/) | — | Hosting & deployment platform |

---

## 📦 Installation

### Prerequisites

Before running this project locally, ensure you have the following installed:

- **Node.js** ≥ 18.x — [Download](https://nodejs.org/)
- **pnpm** ≥ 8.x — [Install](https://pnpm.io/installation)

  ```bash
  npm install -g pnpm
  ```

- An **OpenAI API key** for ChatGPT-powered question generation.

### Clone the Repository

```bash
git clone https://github.com/kuldeep0291-hub/AIHCG.git
cd AIHCG
```

### Install Dependencies

```bash
pnpm install
```

### Configure Environment Variables

Create a `.env.local` file in the project root and add the following:

```env
# OpenAI API key for dynamic question generation (required)
OPENAI_API_KEY=your_openai_api_key_here

# LinkedIn third-party search API key for alumni discovery (required)
# e.g. from RapidAPI or a compatible LinkedIn search provider
LINKEDIN_API_KEY=your_linkedin_api_key_here

# Base URL (optional, for self-hosted or custom AI endpoints)
# AI_BASE_URL=https://api.openai.com/v1
```

---

## 🚀 Running Locally

### Start the Development Server

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to view the application.

### Build for Production

```bash
pnpm build
```

### Start the Production Server

```bash
pnpm start
```

The server runs on port `3000` by default. To use a different port:

```bash
pnpm start -p 8080
```

### Available Scripts

| Script | Command | Description |
|---|---|---|
| `dev` | `pnpm dev` | Start the development server with hot reload |
| `build` | `pnpm build` | Build the application for production |
| `start` | `pnpm start` | Start the production server (after `build`) |
| `lint` | `pnpm lint` | Run ESLint to check for code issues |

---

## 🔮 Future Improvements

- **Expanded Parameter Set** — Introduce additional evaluation dimensions such as communication ability, collaborative mindset, and publication or market awareness.
- **Additional Career Domains** — Extend the model to evaluate suitability for further career paths such as industry engineering roles, public sector positions, or creative fields.
- **Personalised Score Reports** — Generate downloadable PDF reports summarising the compatibility score, parameter breakdown, and recommended next steps.
- **Mentor Matching** — Connect students directly with mentors in their detected career domain based on compatibility profiles.
- **Longitudinal Tracking** — Allow returning users to re-evaluate over time and track how their compatibility score evolves.
- **Institutional Integrations** — Partner with universities to embed Career Guru directly into student portals and career services platforms.
- **Multilingual Support** — Extend the chatbot interface to support multiple languages for broader accessibility.

---

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

<div align="center">

Made with ❤️ using [Next.js](https://nextjs.org/), [Vercel AI SDK](https://sdk.vercel.ai/), and [shadcn/ui](https://ui.shadcn.com/)

</div>