```
classDiagram
    class IModel {
        <<interface>>
        +getAll(): array
        +getOne(id): ?object
        +create(data): object
        +update(id, data): bool
        +delete(id): bool
    }

    class UserModel {
        +getAll(): array
        +getOne(id): ?User
        +create(data): User
        +update(id, data): bool
        +delete(id): bool
        -dbConn
    }

    class ProductModel {
        +getAll(): array
        +getOne(id): ?Product
        +create(data): Product
        +update(id, data): bool
        +delete(id): bool
        -dbConn
    }

    %% Relationships
    IModel <|.. UserModel
    IModel <|.. ProductModel

    %% Example consumer that depends on the interface (polymorphism)
    class Controller {
        +index(): array
        +show(id): object
        -model: IModel
    }
    Controller --> IModel : uses
```