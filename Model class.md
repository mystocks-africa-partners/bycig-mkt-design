```
classDiagram
    class IModel {
        <<interface>>
        +getAll(): array
        +getOne(id): ?object
    }

    class UserModel {
        +getAll(): array
        +getOne(id): ?User
        -dbConn
    }

    class ProductModel {
        +getAll(): array
        +getOne(id): ?Product
        -dbConn
    }

    IModel <|.. UserModel
    IModel <|.. ProductModel
