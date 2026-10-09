# 8. UML Package Diagram — Proposed Application Layers

**Scope:** Proposed folder/package responsibilities and dependencies for the Hannah Printing Shop System.

```mermaid
flowchart TD
    subgraph Presentation["pkg: Presentation"]
        Pages[Pages and UI Components]
    end

    subgraph Controllers["pkg: Controllers"]
        RequestController[Request Controller]
        StatusController[Status Controller]
        ServiceController[Service Controller]
        UserController[User Controller]
    end

    subgraph Services["pkg: Business Services"]
        RequestService[Request Service]
        QueueService[Queue Service]
        FileService[File Service]
        PaymentService[Payment Record Service]
    end

    subgraph DataAccess["pkg: Data Access / ORM"]
        Models[Domain Models and Repositories]
    end

    subgraph Storage["pkg: Storage"]
        DB[(Relational Database)]
        Files[(Private Uploaded Files)]
    end

    Pages --> Controllers
    Controllers --> Services
    Services --> Models
    Models --> DB
    FileService --> Files
