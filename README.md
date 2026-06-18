# PortfolioCore

PortfolioCore is a dynamic personal portfolio management application built with ASP.NET Core MVC. It includes a public portfolio interface and admin-oriented management screens for maintaining portfolio content such as skills, experience, education, services, projects, testimonials, social media links, statistics, and messages.

This project demonstrates ASP.NET Core MVC, Entity Framework Core Code First, SQL Server, Razor Views, ViewComponents, and CRUD-based content management.

## Features

### Public Portfolio UI

- Dynamic About, Skills, Experience, Education, Services, Portfolio, Testimonials, and Contact sections
- Database-driven content rendering
- Portfolio/category listing structure
- Dynamic statistics area
- Contact/message form
- Responsive UI based on a portfolio template

### Admin / Management Screens

- CRUD screens for portfolio content
- Skill management
- Experience management
- Project/portfolio management
- Testimonial management
- Social media management
- Dynamic statistics screen
- Custom 404 error page

## Tech Stack

- ASP.NET Core MVC 6.0
- C#
- Entity Framework Core 6
- EF Core Code First Migrations
- SQL Server
- Razor Views
- ViewComponent architecture
- HTML5, CSS3, Bootstrap
- JavaScript

## Project Structure

```text
PortfolioCore/
├── PortfolioCoreDay.sln
├── PortfolioCoreDay/
│   ├── Context/
│   │   └── PortfolioContext.cs
│   ├── Controllers/
│   ├── Entities/
│   ├── Migrations/
│   ├── Models/
│   ├── ViewComponents/
│   ├── Views/
│   ├── wwwroot/
│   ├── Program.cs
│   ├── appsettings.json
│   └── PortfolioCoreDay.csproj
└── README.md
```

## Requirements

Before running the project, make sure the following tools are installed:

- .NET 6 SDK
- SQL Server, SQL Server Express, LocalDB, or SQL Server running in Docker
- Visual Studio 2022 or Visual Studio Code
- EF Core CLI tools

Install EF Core CLI tools if they are not already installed:

```bash
dotnet tool install --global dotnet-ef
```

If the tool is already installed, update it:

```bash
dotnet tool update --global dotnet-ef
```

## Database Setup

The project uses SQL Server with Entity Framework Core Code First migrations.

The database connection is read from:

```text
PortfolioCoreDay/appsettings.json
```

Default local configuration:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=PortfolioDayDb;Trusted_Connection=True;TrustServerCertificate=True;"
}
```

For team or production-like usage, keep machine-specific values out of source control and override the connection string with user secrets:

```bash
dotnet user-secrets init --project PortfolioCoreDay/PortfolioCoreDay.csproj

dotnet user-secrets set "ConnectionStrings:DefaultConnection" "Server=localhost;Database=PortfolioDayDb;Trusted_Connection=True;TrustServerCertificate=True;" --project PortfolioCoreDay/PortfolioCoreDay.csproj
```

If you use SQL Server in Docker, use a SQL authentication connection string instead:

```bash
dotnet user-secrets set "ConnectionStrings:DefaultConnection" "Server=localhost,1433;Database=PortfolioDayDb;User Id=sa;Password=Your_password123;TrustServerCertificate=True;" --project PortfolioCoreDay/PortfolioCoreDay.csproj
```

Apply migrations:

```bash
dotnet ef database update --project PortfolioCoreDay/PortfolioCoreDay.csproj --startup-project PortfolioCoreDay/PortfolioCoreDay.csproj
```

This command creates the `PortfolioDayDb` database and required tables.

## How to Run

Clone the repository:

```bash
git clone https://github.com/FatmaBuseBorlu/PortfolioCore.git
```

Navigate into the project folder:

```bash
cd PortfolioCore
```

Restore dependencies:

```bash
dotnet restore
```

Apply database migrations:

```bash
dotnet ef database update --project PortfolioCoreDay/PortfolioCoreDay.csproj --startup-project PortfolioCoreDay/PortfolioCoreDay.csproj
```

Run the application:

```bash
dotnet run --project PortfolioCoreDay/PortfolioCoreDay.csproj
```

Open the application in your browser using the localhost URL shown in the terminal.

## Main Routes

```text
/Default/Index                  Public portfolio page
/Skill/SkillList                Skill management
/Experience/ExperienceList      Experience management
/Portfolio/ProjectList          Portfolio/project management
/Testimonial/TestimonialList    Testimonial management
/SocialMedia/Index              Social media management
/Statistics/Index               Statistics dashboard
```

## What I Practiced

- ASP.NET Core MVC application structure
- Entity Framework Core Code First migrations
- SQL Server integration
- Razor Views and ViewComponents
- CRUD operations with relational entities
- Dynamic content rendering from database
- Admin-oriented management screens
- Custom route and error page handling
- Template customization in an ASP.NET Core project
- Environment-based configuration with `appsettings.json` and user secrets

## Future Improvements

- Add authentication and authorization for admin pages
- Add image upload support for portfolio items
- Add pagination and filtering for admin lists
- Add seed data for faster local setup
- Add unit/integration tests
- Add Docker Compose support for easier local development
- Upgrade the project to a newer .NET version

## Repository

GitHub: https://github.com/FatmaBuseBorlu/PortfolioCore