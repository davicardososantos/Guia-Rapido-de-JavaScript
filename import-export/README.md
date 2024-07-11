# Import e Export em JavaScript

## Import

A instrução `import` é usada para trazer módulos, funções, objetos ou primitivas exportadas de outros arquivos ou módulos para o escopo atual.

### Sintaxe Básica

A sintaxe básica de um `import` é:

```javascript
import something from 'module-name';
```

Aqui está um detalhamento dos componentes dessa instrução:

- `something`: Pode ser um objeto, função, classe, constante ou qualquer valor exportado pelo módulo. O nome usado aqui é o que você usará no seu código para referenciar o que foi importado.
- `'module-name'`: O caminho ou nome do módulo de onde você está importando. Pode ser um módulo npm, um caminho relativo ou absoluto para um arquivo no seu projeto.

### Exemplos de Uso

##### 1. Importando um módulo padrão:
Se um módulo exporta uma única entidade como padrão:

```javascript
// module.js
export default function() {
  console.log('Hello from the module!');
}

// main.js
import greet from './module';
greet(); // Outputs: Hello from the module!
```

##### 2. Importando várias entidades nomeadas:
Se um módulo exporta várias entidades:

```javascript
// module.js
export const name = 'Vue.js';
export function greet() {
  console.log('Hello from Vue.js!');
}

// main.js
import { name, greet } from './module';
console.log(name); // Outputs: Vue.js
greet(); // Outputs: Hello from Vue.js!

```

##### 3. Importando tudo de um módulo:
Você pode importar tudo de um módulo como um objeto:

```javascript
// module.js
export const name = 'Vue.js';
export function greet() {
  console.log('Hello from Vue.js!');
}

// main.js
import * as module from './module';
console.log(module.name); // Outputs: Vue.js
module.greet(); // Outputs: Hello from Vue.js!
```

##### 4. Renomeando importações:
Você pode renomear importações para evitar conflitos de nome:

```javascript
// module.js
export const name = 'Vue.js';
export function greet() {
  console.log('Hello from Vue.js!');
}

// main.js
import { name as frameworkName, greet as sayHello } from './module';
console.log(frameworkName); // Outputs: Vue.js
sayHello(); // Outputs: Hello from Vue.js!
```

## Export

A instrução `export` é usada para exportar funções, objetos ou primitivas de um arquivo para que possam ser reutilizadas em outros arquivos e módulos. Existem duas principais maneiras de exportar código: exportações nomeadas e exportações padrão.

### Sintaxe Básica

##### Exportações Nomeadas
Você pode exportar várias entidades de um módulo usando exportações nomeadas. Isso é útil quando você deseja exportar múltiplas variáveis ou funções do mesmo módulo.

```javascript
export const name = 'Vue.js';
export function greet() {
  console.log('Hello from Vue.js!');
}
```

##### Exportação Padrão
Cada módulo pode ter uma única exportação padrão. Isso é útil quando o módulo exporta uma única entidade principal.

```javascript
export default function() {
  console.log('Hello from the module!');
}
```

#### Exemplos de Uso

##### 1. Exportando Constantes e Funções

```javascript
export const name = 'Vue.js';
export function greet() {
  console.log('Hello from Vue.js!');
}
```

##### 2. Exportação Padrão

```javascript
const name = 'Vue.js';
const greet = function() {
  console.log('Hello from Vue.js!');
}

export default greet;
```

##### 3. Exportando Múltiplas Entidades com Exportação Padrão
Embora um módulo possa ter apenas uma exportação padrão, ele ainda pode ter exportações nomeadas adicionais.


```javascript
const name = 'Vue.js';
const greet = function() {
  console.log('Hello from Vue.js!');
}

export default greet;
export { name };
```

##### 4. Exportação Padrão com Objeto Vazio
Embora exportar um objeto vazio por si só possa não ser muito útil, a exportação padrão é frequentemente usada para exportar objetos que contêm várias propriedades e métodos. Aqui está um exemplo mais realista:


```javascript
// module.js
export default {
  name: 'Vue.js',
  greet() {
    console.log('Hello from Vue.js!');
  }
};

// main.js
import myModule from './module';  // Importa o módulo

console.log(myModule.name); // Outputs: Vue.js
myModule.greet(); // Outputs: Hello from Vue.js!
```

## Conclusão
O sistema de módulos ES6 (import e export) em JavaScript oferece uma maneira eficiente de organizar, reutilizar e manter seu código. Ele permite dividir seu código em módulos menores e mais gerenciáveis, facilitando a manutenção e a colaboração em projetos maiores.


