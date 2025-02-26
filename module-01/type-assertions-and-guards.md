# Type Assertions

`Type Assertions` são utilizadas para manipular e validar os tipos em tempo de execução, permitindo ao desenvolvedor informar ao TypeScript qual é o tipo esperado para determinada variável.

### Sintaxe:
Existem duas formas principais de realizar uma `Type Assertion` em TypeScript:

1. **Usando `as`**:
```typescript
let someValue: any = "Hello TypeScript";
let stringLength: number = (someValue as string).length;
```

2. **Usando `<>` (não recomendado em JSX/TSX)**:
```typescript
let someValue: any = "Hello TypeScript";
let stringLength: number = (<string>someValue).length;
```

### Características:
- Permite ao desenvolvedor informar explicitamente o tipo de uma variável.
- Útil quando o TypeScript não consegue inferir corretamente o tipo.
- Não altera o valor ou comportamento do código em tempo de execução.
- Pode levar a erros se o tipo for forçado incorretamente.

### Quando usar?
- Quando temos valores do tipo `any` ou `unknown` e queremos garantir um tipo mais específico.
- Quando estamos lidando com APIs que não possuem tipagem adequada.

---

## Type Guards

`Type Guards` são usados para restringir tipos em tempo de execução, garantindo que um determinado valor siga um tipo específico antes de ser utilizado.

### Exemplo:
```typescript
function processValue(value: string | number) {
  if (typeof value === 'string') {
    console.log(value.toUpperCase());
  } else {
    console.log(value.toFixed(2));
  }
}

processValue('1'); // Output: "1"
processValue(1);   // Output: "1.00"
```

### Características:
- `typeof`: Verifica se o valor é `string`, `number`, `boolean`, `symbol`, `undefined`, `object` ou `function`.
- `instanceof`: Verifica se um objeto pertence a uma determinada classe.
- `in`: Verifica se uma propriedade existe em um objeto.

### Exemplo com `instanceof`:
```typescript
class Dog {
  bark() {
    console.log("Woof!");
  }
}

class Cat {
  meow() {
    console.log("Meow!");
  }
}

function makeSound(animal: Dog | Cat) {
  if (animal instanceof Dog) {
    animal.bark();
  } else {
    animal.meow();
  }
}
```

### Exemplo com `in`:
```typescript
type User = { name: string; email: string };
type Admin = { name: string; permissions: string[] };

type Person = User | Admin;

function checkPerson(person: Person) {
  if ('permissions' in person) {
    console.log("This is an admin with permissions:", person.permissions);
  } else {
    console.log("This is a regular user:", person.name);
  }
}
```

### Quando usar?
- Quando temos tipos `union` e precisamos diferenciar os casos antes de acessar propriedades específicas.
- Quando queremos evitar erros ao acessar métodos que só existem em certos tipos.
- Quando queremos garantir uma manipulação mais segura dos dados em tempo de execução.

