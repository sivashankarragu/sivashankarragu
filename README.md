<div align="center">

# 🛠️ Skills & Tech Showcase

**Full-stack engineering · Clean Architecture · AI web agents · Real-time UX**

![.NET](https://img.shields.io/badge/.NET_8-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23_12-239120?style=for-the-badge&logo=csharp&logoColor=white)
![Angular](https://img.shields.io/badge/Angular_21-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![RxJS](https://img.shields.io/badge/RxJS-B7178C?style=for-the-badge&logo=reactivex&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)
![xUnit](https://img.shields.io/badge/xUnit-5C2D91?style=for-the-badge&logo=dotnet&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white)

</div>

---

## ✨ At a Glance

| Area | Skills Demonstrated |
|------|---------------------|
| 🧱 **Architecture** | Clean Architecture, Domain-Driven layering, dependency inversion, provider/strategy pattern |
| ⚙️ **Backend** | ASP.NET Core Web API, background workers, Server-Sent Events, typed HTTP clients |
| 🎨 **Frontend** | Angular standalone components, Signals, RxJS, Tailwind CSS, responsive UI |
| 🗄️ **Data** | PostgreSQL, Dapper, versioned SQL migrations, seed data, in-memory fallback |
| 🤖 **AI / Automation** | Integration with autonomous web-agent APIs, async job orchestration |
| 🧪 **Quality** | Unit & integration testing, warnings-as-errors, nullable reference types |
| 🔐 **DevOps & Security** | Environment-based config, user secrets, scripted migrations |

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

## ⚙️ Backend Engineering — .NET 8 / C# 12

- 🌐 RESTful **ASP.NET Core Web API** with **Swagger / OpenAPI** documentation
- 🔄 **Background job processing** with `BackgroundService` and an in-process work queue
- 📡 **Real-time streaming** of progress updates via **Server-Sent Events (SSE)**
- 🔌 **Typed `HttpClient`** integrations using `IHttpClientFactory`
- ⚡ **In-memory caching** with `Microsoft.Extensions.Caching.Memory`
- 🧹 Strict compiler settings: **nullable reference types**, **implicit usings**, **warnings treated as errors**

---

## 🎨 Frontend Engineering — Angular 21

- 🧩 Modern **standalone components** with a feature-based folder structure (`core/`, `features/`)
- 📶 Reactive state with **Angular Signals** and **RxJS** streams
- 📡 Live UI updates consuming **SSE / `EventSource`** streams
- 💅 Utility-first styling with **Tailwind CSS 4** + PostCSS
- 🛣️ Client-side routing, typed API service layer and shared models
- 🧼 Consistent formatting with **Prettier** and **EditorConfig**

---

## 🗄️ Data & Persistence

- 🐘 **PostgreSQL** as the primary data store
- 🪶 Lightweight, performant data access with **Dapper** + **Npgsql**
- 📜 **Versioned SQL migrations** and **seed scripts**, applied via a **PowerShell** runner
- 🧪 Zero-setup **in-memory persistence** mode for demos and local development

---

## 🤖 AI & Automation

- Integration with **autonomous AI web-agent APIs** for live, multi-step web research
- **Asynchronous orchestration** — long-running agent tasks tracked as sessions with progress events
- **Mock provider with scenarios** (`Success`, `Partial`, `Failure`, `Empty`) for reliable demos and resilient UX design

---

## 🧪 Testing & Quality

- ✅ **Unit tests** with **xUnit**
- 🔗 **Integration tests** with `WebApplicationFactory` (`Microsoft.AspNetCore.Mvc.Testing`)
- 📊 Code coverage via **Coverlet**
- 🧭 Graceful handling of partial, empty and failed results end to end

---

## 🔐 Configuration & Security

- 🔑 Secrets kept out of source control — **environment variables** & **.NET User Secrets**
- 📄 Documented `.env.example` with safe placeholder values only
- 🧭 Hierarchical configuration (`Section__Key` → `Section:Key`) following ASP.NET Core conventions

---

## 🧰 Tooling

<div align="center">

![Visual Studio](https://img.shields.io/badge/Visual_Studio-5C2D91?style=flat-square&logo=visualstudio&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=flat-square&logo=visualstudiocode&logoColor=white)
![Angular CLI](https://img.shields.io/badge/Angular_CLI-DD0031?style=flat-square&logo=angular&logoColor=white)
![npm](https://img.shields.io/badge/npm-CB3837?style=flat-square&logo=npm&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Prettier](https://img.shields.io/badge/Prettier-F7B93E?style=flat-square&logo=prettier&logoColor=black)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat-square&logo=anthropic&logoColor=white)

</div>

---

<div align="center">

⭐ *Built with clean code, solid architecture and a love for great developer experience.* ⭐

</div>
