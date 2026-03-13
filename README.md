# 💕 DatingApp — Real-Time Social Matching Platform

[![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-512BD4?style=flat-square&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com)
[![Angular](https://img.shields.io/badge/Angular-DD0031?style=flat-square&logo=angular&logoColor=white)](https://angular.io)
[![SignalR](https://img.shields.io/badge/SignalR-512BD4?style=flat-square&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/apps/aspnet/signalr)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://postgresql.org)
[![CloudinaryBadge](https://img.shields.io/badge/Cloudinary-3448C5?style=flat-square&logo=cloudinary&logoColor=white)](https://cloudinary.com)

A feature-rich social matching web application with real-time messaging, photo management, and intelligent user matching. Built following industry best practices with a clean layered architecture.

## ✨ Features

- 👤 **User profiles** — photo upload via Cloudinary, bio, interests, age filtering
- 💞 **Like & match system** — mutual likes create a match and unlock chat
- 💬 **Real-time messaging** — instant chat via SignalR WebSockets
- 🔔 **Presence tracking** — see who's online right now
- 🔍 **Smart filtering** — filter by age, gender, location, last active
- 📸 **Photo management** — upload, set main photo, delete — powered by Cloudinary
- 🔐 **JWT authentication** with refresh token rotation
- 📄 **Pagination** — server-side paged member lists

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Angular 17 · TypeScript · Bootstrap · NgRx |
| Backend | ASP.NET Core 8 · C# · Repository + Unit of Work pattern |
| Real-time | ASP.NET Core SignalR |
| Database | PostgreSQL · Entity Framework Core 8 |
| Media | Cloudinary API (photo upload and storage) |
| Auth | JWT Bearer + Refresh Tokens |
| Mapping | AutoMapper |

## 🏗️ Architecture

```
DatingApp/
├── API/                    # ASP.NET Core Web API
│   ├── Controllers/        # Thin controllers — logic in services
│   ├── Data/               # EF Core DbContext, Migrations, Repositories
│   ├── DTOs/               # Data transfer objects (no domain leakage)
│   ├── Entities/           # Domain models (AppUser, Message, Photo, Like)
│   ├── Interfaces/         # Repository and service interfaces
│   ├── Services/           # Business logic (TokenService, PhotoService)
│   ├── SignalR/            # Hubs (MessageHub, PresenceHub)
│   └── Helpers/            # AutoMapper profiles, pagination, query params
└── client/                 # Angular SPA
    ├── src/app/
    │   ├── members/        # Profile list, detail, edit, photo editor
    │   ├── messages/       # Inbox and real-time chat
    │   ├── matches/        # Mutual likes view
    │   └── _services/      # Angular services for API calls + SignalR
    └── environments/
```

## 🚀 Getting Started

### Prerequisites
- .NET 8 SDK
- Node.js 20+
- PostgreSQL (or Docker)

```bash
git clone https://github.com/joshivignesh/DatingApp.git
cd DatingApp

# Start backend
cd API
dotnet restore
dotnet run

# Start frontend (new terminal)
cd ../client
npm install
ng serve
```

App runs at `http://localhost:4200`

## 🌱 Database Seeding

The app seeds 10 demo users automatically on first run. Login with any seeded user to explore the app.

## 👤 Author

**Vignesh Joshi** — [LinkedIn](https://linkedin.com/in/joshivignesh) · [GitHub](https://github.com/joshivignesh)
