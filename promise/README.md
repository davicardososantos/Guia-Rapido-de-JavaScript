## O que é Promise? (Promessa)

Uma *Promise* em JavaScript representa uma operação que ainda não foi concluída, mas que espera-se ser completada no futuro. É como uma promessa que pode ter um resultado positivo ou negativo.

### Analogias para Entender Promises

#### Encomenda de um Produto Online

Imagine que você faz uma compra online:

1. **Pendente**: Você fez o pedido, mas ainda não sabe quando ele será entregue.
2. **Positiva**: O pedido é processado e você recebe o produto.
3. **Negativa**: O pedido é cancelado ou o produto não está disponível.

#### Pedido de Casamento

Outro exemplo é um pedido de casamento:

1. **Pendente**: A pessoa está pensando na resposta.
2. **Positiva**: A pessoa diz "sim".
3. **Negativa**: A pessoa diz "não".

#### Entrevista de Emprego
Você se candidatou a um emprego e está aguardando a resposta:

1. **Pendente**: Você foi entrevistado e está esperando a resposta da empresa.
2. **Positiva**: Você é aceito para o emprego.
3. **Negativa**: Você não é aceito para o emprego.

### Promises no JavaScript

No contexto do JavaScript, Promises são usadas para manipular operações assíncronas, como:

- Manipulação de dados
- Cálculos
- Gerar arquivos (PDF, CSV, etc.)
- Comunicação com APIs (AJAX)

#### Estrutura de uma Promise

Uma Promise é criada com dois parâmetros: `resolve` e `reject`.

- `resolve`: Indica que a operação foi concluída com sucesso.
- `reject`: Indica que a operação falhou.

#### Exemplo de Uso

```javascript
// Criação de uma Promise
let entrevistaEmprego = new Promise((resolve, reject) => {
  let candidatoAceito = true;

  if (candidatoAceito) {
    resolve("Parabéns! Você foi aceito para o emprego.");
  } else {
    reject("Lamentamos, mas você não foi aceito para o emprego.");
  }
});

// Manipulação da Promise
entrevistaEmprego
  .then(mensagem => {
    console.log(mensagem); // Se a promessa for resolvida
  })
  .catch(erro => {
    console.error(erro); // Se a promessa for rejeitada
  })
  .finally(() => {
    console.log("Processo da entrevista finalizado."); // Sempre executado
  });

```

### Estados de uma Promise
- **Pendente**: Estado inicial, a promessa ainda não foi cumprida nem rejeitada.
- **Cumprida (Resolved)**: A operação foi concluída com sucesso.
- **Rejeitada (Rejected)**: A operação falhou.

### Métodos de Manipulação
- `.then()`: Chamado quando a promessa é cumprida.
- `.catch()`: Chamado quando a promessa é rejeitada.
- `.finally()`: Chamado quando a promessa é concluída (cumprida ou rejeitada).