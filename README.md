# WorkShop (TroubleTraining)

A .NET solution with a multi-service architecture: API server, BFF (Backend for Frontend), Identity Server, Device, and Scheduler services.

## Solution structure

| Area | Description |
|------|-------------|
| **APIServer** | Main API with GraphQL, WebHooks, and CQRS (API, Application, Domain, Persistence) |
| **BFF** | Backend for Frontend with React client (API, Domain) |
| **IdentityServer** | Authentication and authorization (API, Application, Domain, Persistence) |
| **Device** | Device-related API and logic (API, Application, Domain) |
| **Scheduler** | Scheduling service (API, Domain) |
| **Shared** | Shared APIs, application logic, domain, and persistence |

## Requirements

- [.NET SDK](https://dotnet.microsoft.com/download)
- [Node.js](https://nodejs.org/) (for BFF ClientApp)
- [Docker](https://www.docker.com/) (optional, for containers)

## Building

Solution file: `Src/TroubleTraining.sln`

```bash
dotnet build Src/TroubleTraining.sln
```

Or use the Nuke build (from repo root):

```bash
./nuke
```

## Running

Run the solution from Visual Studio or Rider, or start individual projects:

```bash
dotnet run --project Src/APIServer/API/APIServer.csproj
dotnet run --project Src/BFF/API/BFF.csproj
dotnet run --project Src/IdentityServer/API/IdentityServer.csproj
```

Docker Compose configs are under `Docker/` for services like Elasticsearch, Beats, and testing.

## Tests

```bash
dotnet test Src/TroubleTraining.sln
```

Tests include unit, integration, API, and benchmarks under `Src/Tests/`.
