# Basic Types

### String
A `string` em TypeScript representa uma sequência de caracteres delimitada por aspas simples (`'`), aspas duplas (`"`), ou crase (`` ` ``) para *template literals*.

#### Exemplo:
```typescript
let firstName: string = "John";
let lastName: string = 'Doe';
let fullName: string = `${firstName} ${lastName}`;
console.log(fullName); // Output: "John Doe"
```

#### Características:
- Suporte a interpolação com *template literals* (` `` `), permitindo a inserção de textos ou variáveis dentro de uma string usando crases.
- Métodos úteis como `.length`, `.toUpperCase()`, `.toLowerCase()`, `.trim()`, entre outros.

### Number
O tipo `number` representa valores numéricos, incluindo inteiros e decimais. Em TypeScript, todos os números são representados internamente como *floating-point numbers* seguindo o padrão IEEE 754.

#### Exemplo:
```typescript
let age: number = 25;
let height: number = 1.75;
let hex: number = 0xff;
let binary: number = 0b1010;
let octal: number = 0o744;
```

#### Características:
- Suporte a números inteiros e de ponto flutuante.
- Suporte a notação hexadecimal (`0x`), binária (`0b`), e octal (`0o`).
- Métodos úteis como `Math.round()`, `Math.floor()`, `Math.ceil()` e `toFixed()`.

### Null
O tipo `null` representa uma ausência intencional de valor.

#### Exemplo:
```typescript
let user: string | null = null;
```

#### Características:
- `null` pode ser atribuído a qualquer tipo se `strictNullChecks` estiver desativado.
- Quando `strictNullChecks` está ativado, `null` só pode ser atribuído a variáveis explicitamente tipadas como `null` ou com *union types*.

### Undefined
O tipo `undefined` representa valores que não foram inicializados.

#### Exemplo:
```typescript
let notAssigned: undefined;
console.log(notAssigned); // Output: undefined
```

#### Características:
- Em `strictNullChecks: true`, `undefined` só pode ser atribuído a variáveis do tipo `undefined` ou com *union types*.
- O `undefined` é frequentemente usado para indicar propriedades não definidas em objetos.
- Funções que não retornam explicitamente algo devolvem `undefined`.

```typescript
function logMessage(): void {
  console.log("Hello, TypeScript!");
}

let result = logMessage();
console.log(result); // Output: undefined
```

### Array
O `array` em TypeScript representa uma coleção de valores do mesmo tipo.

#### Exemplo
```typescript
let listaCompra: string[] = ['maçã', 'banana', 'laranja']; 
let listaCompra2: [string] = ['maçã']; // Tupla de um único elemento

let resultados: number[] = [1, 2, 3, 4];
let resultadosTupla: [number] = [1]; // Tupla de um único número
```

#### Características:
- Pode ser definido com `tipo[]` para representar uma lista homogênea.
- Tuplas `[tipo]` podem ser usadas para listas de tamanho fixo.

### Any
O tipo `any` é um *Union Type* de todos os tipos primitivos e complexos. Ele permite que uma variável armazene qualquer tipo de dado, desativando a verificação de tipos.

#### Exemplo:
```typescript
let valor: any = 5;
valor = "Agora sou uma string";
valor = true; // Pode assumir qualquer tipo
```

#### Características:
- Permite flexibilidade, mas reduz a segurança do TypeScript.
- Deve ser evitado sempre que possível para manter tipagem forte.

### Boolean
O tipo `boolean` representa um valor lógico que pode ser `true` ou `false`.

#### Exemplo:
```typescript
let isCompleted: boolean = false;
let hasAccess: boolean = true;
```

#### Características:
- Usado para controle de fluxo e condições.
- Aceita apenas `true` ou `false` como valores válidos.

