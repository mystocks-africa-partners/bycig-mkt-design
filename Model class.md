# Model Classes

The models are part of the MVC architecture. They encompass all db queries and operations. 

The models are structured to have polymorphism where there is are standardized method signatures aligning to CRUD (create, read, update, delete).

This standardization has been defined in the IModel interface (conventional naming adhered)

```mermaid
classDiagram
    class IModel {
        <<interface>>
        +getAll(): array
        +getOne(id): ?object
        +delete(id): void
        +update(id): void
        +create(assoc_array): void
    }

    class UserModel {
        +getAll(): assoc_array<User>
        +getOne(id): ?User
        +delete(id): void
        +update(id): void
        +create(assoc_array): void
    }

    class ProposalModel {
        +getAll(): assoc_array<Proposal>
        +getOne(id): ?Proposal
        +delete(id): void
        +update(id): void
        +create(assoc_array): void
    }

    class HoldingModel{
        +getAll(): assoc_array<Holding>
        +getOne(id): ?Holding
        +delete(id): void
        +update(id): void
        +create(assoc_array): void
    }

    IModel <|.. UserModel
    IModel <|.. ProposalModel
    IModel <|.. HoldingsModel
