

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

    IModel <|.. UserModel
    IModel <|.. ProposalModel
