# API Simples de Loja

```mermaid
classDiagram
    class Cliente {
        +int id
        +String nome
        +String email
        +String telefone
        +int endereco_id
    }

    class Endereco {
        +int id
        +String rua
        +String numero
        +String complemento
        +String bairro
        +String cidade
        +String estado
        +String cep
    }

    class Compra {
        +int id
        +Date data
        +float total
        +int cliente_id
    }

    class ComprasProdutos {
        +int id
        +int compra_id
        +int produto_id
        +int quantidade
        +float preco_unitario
    }

    class Produto {
        +int id
        +String nome
        +String descricao
        +float preco
        +int estoque
    }

    Cliente "1" --> "0..1" Endereco : reside
    Cliente "1" --> "0..*" Compra : realiza
    Compra "1" --> "0..*" ComprasProdutos : contém
    Produto "1" --> "0..*" ComprasProdutos : é parte de
