<div align="center">

# 🛠️ Skills & Tech Showcase

**Full-stack engineering · Clean Architecture · AI web agents · Real-time UX**

![.NET](https://img.shields.io/badge/.NET_8-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23_12-239120?style=for-the-badge&logo=csharp&logoColor=white)
![Angular](https://img.shields.io/badge/Angular_21-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js_16-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React_19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![RxJS](https://img.shields.io/badge/RxJS-B7178C?style=for-the-badge&logo=reactivex&logoColor=white)
![TinyFish](https://img.shields.io/badge/TinyFish_Web_Agents-0EA5E9?style=for-the-badge)
![Zod](https://img.shields.io/badge/Zod-3E67B1?style=for-the-badge&logo=zod&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)
![xUnit](https://img.shields.io/badge/xUnit-5C2D91?style=for-the-badge&logo=dotnet&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white)

</div>

---

## 🧗 My Journey: From Debugging by Hand to Building AI Agents

I started writing code professionally in **2015**, long before AI was part of a developer's day.
No copilots, no chatbots: just documentation, Stack Overflow, breakpoints, and a lot of patience.

I learned by **reading other people's code**, **stepping through bugs line by line**, and **fighting with errors until they made sense**.
Those years taught me how software really works under the surface, and that is exactly what I bring to building with AI today.

```
2015 ──▶ Started out: C#, .NET, SQL. Learned by debugging, breaking things and fixing them
   │
   ├──▶ Grew into full-stack: REST APIs, front-end frameworks, databases, real production issues
   │
   ├──▶ Learned to design, not just code: Clean Architecture, testing, maintainable systems
   │
   ├──▶ AI arrived: adopted AI tools early, and used my fundamentals to judge what they produce
   │
   └──▶ Today: building AI web agents that browse, verify and act on the live web
```

> 💡 **What hasn't changed since 2015:** understand the problem, read the code, trust evidence over guesses.
> AI made me faster. The years of debugging taught me where to look when it gets things wrong.

---

## ✨ At a Glance

| Area | Skills Demonstrated |
|------|---------------------|
| 🧱 **Architecture** | Clean Architecture, Domain-Driven layering, dependency inversion, provider/strategy pattern |
| ⚙️ **Backend** | ASP.NET Core Web API, Next.js route handlers, background workers, Server-Sent Events, typed HTTP clients |
| 🎨 **Frontend** | Angular standalone components, Signals, RxJS, React 19, Framer Motion, Tailwind CSS, responsive UI |
| 🗄️ **Data** | PostgreSQL, Dapper, versioned SQL migrations, seed data, in-memory fallback |
| 🤖 **AI Web Agents** | Browser agents on live websites, parallel agent orchestration, structured output, authenticated sessions, cost control |
| 🧪 **Quality** | Unit & integration testing, offline test scripts, warnings-as-errors, nullable reference types, strict TypeScript |
| 🔐 **DevOps & Security** | Environment-based config, user secrets, scripted migrations, secrets kept server-side |

---

## 🚀 Featured Agent Projects

### 🧭 [GoMigo](https://github.com/sivashankarragu/go-mi-go-agent): *your next move, figured out*
Tell it where you are, how much time and money you have, and your mood. AI web agents research the live web in a real browser and bring back places that fit, ranked against your constraints.
- Every venue is marked **Verified**, **Partially Verified** or **Unverified**, with its source link and an evidence excerpt
- Watch the agents work: a live activity feed with progress messages and per-step browser screenshots
- `robots.txt` is checked before any agent visits a page

`.NET 8` `Angular 21` `Tailwind 4` `PostgreSQL` `TinyFish` · 🏆 TinyFish Hackathon

### 🐟 [Tavocina](https://github.com/sivashankarragu/tavocina-agent): *from fridge to cart*
Type what's in your fridge. Three browser agents fetch real, rated recipes from live sites in parallel (Italian, Indian, Mexican), then a fourth agent adds the missing ingredients to a real grocery cart. It never checks out.
- First recipe card in **~5 s**, then verified in place by a live browser agent
- Live browser view of every agent, with progress narration and items that fly into the basket as the agent adds them
- Real ratings and calories only; anything a page doesn't list shows as "not listed"

`Next.js 16` `React 19` `TypeScript` `Framer Motion` `zod` `TinyFish` · 🏆 TinyFish Hackathon

---

## 🧱 Architecture & Design

```
┌──────────────┐    ┌───────────────────┐    ┌──────────────┐
│  Api         │───▶│  Application      │───▶│  Domain      │
│  Controllers │    │  Use cases, ports │    │  Entities    │
└──────┬───────┘    └─────────▲─────────┘    └──────────────┘
       │                      │ implements
       │            ┌─────────┴─────────┐
       └───────────▶│  Infrastructure   │──▶ PostgreSQL · External APIs · Queue
                    └───────────────────┘
```

- **Clean Architecture** — strict separation of Domain, Application, Infrastructure and API layers
- **Dependency Inversion** — business logic depends on abstractions, never on frameworks
- **Pluggable providers** — swap persistence (`Postgres` ↔ `InMemory`) or external services (`Mock` ↔ real) through configuration alone
- **Options pattern** — strongly typed, validated configuration
- **Centralised error handling** — global exception handler returning RFC 7807 `ProblemDetails`

---

## 🤖 AI Web Agents

### How the agent pipeline works
```
User input ──▶ Search (find the right page, ~2 s)
           ──▶ Fetch  (read clean page text, ~2 s)  ──▶ fast first result
           ──▶ Agent  (real browser: click, scroll, verify, act) ──▶ verified result
           ──▶ Schema validation ──▶ live updates to the UI over SSE
```

- 🧭 **Right tool for each step** — search to *find* a page, fetch to *read* it, and a browser agent only to *act* or when a page needs a real browser. Faster and much cheaper than sending an agent everywhere
- 🔀 **Parallel orchestration** — several agents run at once, each streaming its own progress, live browser view and result
- 🚦 **Concurrency control** — a priority-aware limiter matches the provider's browser limit, so important tasks (like the cart) go first
- ⏱️ **Queue-aware deadlines** — separate time limits for waiting for a browser and for the run itself, so the UI never spins forever
- 🧾 **Structured output** — agents return JSON in a defined schema, validated again with **zod** before it reaches the UI
- 🛟 **Fallbacks at every layer** — if an agent fails or times out, the fetched result is shown; dropped streams are recovered by polling the run
- 💸 **Cost control** — run budgets, duration caps, and explicit cancellation of abandoned runs (closing a stream doesn't stop a paid run)
- 🔐 **Authenticated sessions** — saved browser login profiles let an agent act inside a signed-in account; passwords and OTPs never go into prompts or logs
- 🛑 **Safety guardrails** — agents are told never to check out or pay; site access is tested with real agent probes before building on it
- 🚫 **No made-up data** — values appear only if a source published them; unknowns are shown as unknown
- 🎭 **Mock providers with scenarios** (`Success`, `Partial`, `Failure`, `Empty`) — the same events as live mode, for reliable demos and resilient UX design
- 📊 **Observability** — every agent call logged with timing, success and run ID, shown in an in-app "under the hood" panel

---

## ⚙️ Backend Engineering — .NET 8 / C# 12

- 🌐 RESTful **ASP.NET Core Web API** with **Swagger / OpenAPI** documentation
- 🔄 **Background job processing** with `BackgroundService` and an in-process work queue
- 📡 **Real-time streaming** of progress updates via **Server-Sent Events (SSE)**
- 🔌 **Typed `HttpClient`** integrations using `IHttpClientFactory`
- ⚡ **In-memory caching** with `Microsoft.Extensions.Caching.Memory`
- 🧹 Strict compiler settings: **nullable reference types**, **implicit usings**, **warnings treated as errors**

### Next.js / Node
- 🛰️ **Next.js 16 route handlers** streaming agent events over SSE, with all API keys kept server-side
- 🧩 Typed SDK integration with streaming callbacks and an event-driven client state machine

---

## 🎨 Frontend Engineering — Angular 21 & React 19

- 🧩 Modern **standalone components** with a feature-based folder structure (`core/`, `features/`)
- 📶 Reactive state with **Angular Signals** and **RxJS** streams
- 📡 Live UI updates consuming **SSE / `EventSource`** streams
- 🎬 **React 19 + Framer Motion** animations tied to real agent events (live browser portholes, cards that morph in as results land)
- 💅 Utility-first styling with **Tailwind CSS 4** + PostCSS
- 🛣️ Client-side routing, typed API service layer and shared models
- ♿ Reduced-motion support and plain-text fallbacks for accessibility
- 🧼 Consistent formatting with **Prettier** and **EditorConfig**

---

## 🗄️ Data & Persistence

- 🐘 **PostgreSQL** as the primary data store
- 🪶 Lightweight, performant data access with **Dapper** + **Npgsql**
- 📜 **Versioned SQL migrations** and **seed scripts**, applied via a **PowerShell** runner
- 🧪 Zero-setup **in-memory persistence** mode for demos and local development

---

## 🧪 Testing & Quality

- ✅ **Unit tests** with **xUnit**
- 🔗 **Integration tests** with `WebApplicationFactory` (`Microsoft.AspNetCore.Mvc.Testing`)
- 📊 Code coverage via **Coverlet**
- 🧰 **Offline test scripts** for agent logic (limiter, parsers, ingredient matching) — no paid agent runs needed
- 🔬 **Cheap live smoke tests** run in stages before spending real agent runs
- 🧭 Graceful handling of partial, empty and failed results end to end

---

## 🔐 Configuration & Security

- 🔑 Secrets kept out of source control — **environment variables** & **.NET User Secrets**
- 📄 Documented `.env.example` with safe placeholder values only
- 🧭 Hierarchical configuration (`Section__Key` → `Section:Key`) following ASP.NET Core conventions
- 🛡️ Agent API keys used only on the server, never in the browser

---

## 🧰 Tooling

<div align="center">

![Visual Studio](https://img.shields.io/badge/Visual_Studio-5C2D91?style=flat-square&logo=visualstudio&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=flat-square&logo=visualstudiocode&logoColor=white)
![Angular CLI](https://img.shields.io/badge/Angular_CLI-DD0031?style=flat-square&logo=angular&logoColor=white)
![npm](https://img.shields.io/badge/npm-CB3837?style=flat-square&logo=npm&logoColor=white)
![pnpm](https://img.shields.io/badge/pnpm-F69220?style=flat-square&logo=pnpm&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Prettier](https://img.shields.io/badge/Prettier-F7B93E?style=flat-square&logo=prettier&logoColor=black)
![ESLint](https://img.shields.io/badge/ESLint-4B32C3?style=flat-square&logo=eslint&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat-square&logo=anthropic&logoColor=white)

</div>

---

<div align="center">

⭐ *Built with clean code, solid architecture and a love for great developer experience.* ⭐

</div>
