# TypeScript Documentation

## Interfaces & Types

No TypeScript, `Interfaces` e `Types` são utilizados para definir a estrutura de objetos, mas cada um tem características distintas e aplicações específicas.

### Interfaces
As `Interfaces` são amplamente utilizadas para definir contratos que podem ser implementados em classes. Elas são particularmente úteis para garantir que um objeto siga um formato específico, além de serem aplicáveis na definição de DTOs (*Data Transfer Objects*).

#### Exemplo:
```typescript
interface Person {
  name: string;
  age: number;
}

const person: Person = { name: "Alice", age: 30 };
```

### Types
Os `Types` são frequentemente utilizados para definir alias de tipos complexos e podem concatenar mais de um tipo, permitindo maior flexibilidade na tipagem. Eles são especialmente úteis para definir *Union Types* e *Intersection Types*.

#### Exemplo:
```typescript
type Employee = {
  position: string;
  salary: number;
};

const employee: Employee = { position: "Developer", salary: 5000 };
```

### Diferenças entre Interfaces e Types

| Característica | Interface | Type |
|--------------|-----------|------|
| Pode ser implementada em classes | ✅ | ❌ |
| Pode ser estendida (`extends`) | ✅ | ✅ |
| Pode definir `union types` (`|`) | ❌ | ✅ |
| Pode definir `intersection types` (`&`) | ❌ | ✅ |
| Suporta declaração `reaberta` (mesmo nome, múltiplas declarações) | ✅ | ❌ |

### Características Principais:
- **Interfaces** são mais utilizadas para definir contratos e são amplamente utilizadas em classes e bibliotecas TypeScript.
- **Types** aceitam tanto valores primitivos (`string`, `number`, `boolean`, etc.) quanto tipos complexos (`object`, `array`, `union types`, etc.).
- **Interfaces** não podem ser atribuídas diretamente a valores primitivos, pois seu objetivo é definir a estrutura de objetos.
- **Types** são frequentemente usados para definir *Union Types* e *Intersection Types*, o que os torna mais flexíveis.

### Quando Usar `Interface` ou `Type`?
- **Use `Interface`** quando precisar definir um contrato reutilizável para objetos, especialmente se for implementado em classes.
- **Use `Type`** quando precisar definir combinações de tipos, como `Union` ou `Intersection`, ou criar alias de tipos complexos.

