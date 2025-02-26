# Complex Types

### Union Types (`|`)
`Union Types` permitem que uma variável possa assumir múltiplos tipos possíveis. Isso é útil quando um valor pode ser de mais de um tipo, como `string` ou `number`, ou quando trabalhamos com estados pré-definidos.

#### Exemplo:
```typescript
type Status = 'success' | 'error' | 'loading';
const requestStatus: Status = 'success'; // Aceita apenas os valores do tipo Status
```

#### Características:
- Permite que uma variável aceite múltiplos tipos pré-definidos.
- Pode ser útil para validar valores esperados em uma aplicação.

### Intersection Types (`&`)
`Intersection Types` combinam múltiplos tipos em um só, criando um novo tipo que contém todas as propriedades dos tipos combinados.

#### Exemplo:
```typescript
type User = { name: string; email: string };
type Admin = { permissions: string[] };
type Admin2 = { age: number };

type AdminUser = User & Admin & Admin2; // {name: string; email: string; permissions: string[]; age: number}

const userAdmin: AdminUser = {
  name: 'Jonh',
  age: 12,
  email: 'email@email.com',
  permissions: ['read', 'delete', 'list', 'change']
};
```

#### Características:
- `Union Types (|)`: Permitem que uma variável tenha mais de um tipo possível.
- `Intersection Types (&)`: Criam um novo tipo que combina todas as propriedades dos tipos utilizados.
- `Union` é útil para situações onde um valor pode ser de múltiplos tipos, enquanto `Intersection` é útil para combinar características de diferentes tipos em um único objeto.

### Aplicações Práticas
- `Union Types` são usados em situações onde há diferentes possibilidades de valores, como status de uma requisição ou tipos de entrada de um formulário.
- `Intersection Types` são úteis para modelar estruturas complexas em sistemas tipados, combinando características de diferentes entidades em um único objeto.

