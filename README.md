
## Getting Started

Neste projeto Flutter, você encontrará uma série de classes e widgets que compõem um aplicativo simples de transferência de valores. Vou explicar cada parte do código:

### Imports:

```dart
import 'package:flutter/material.dart';
```
Este importa o pacote `material`, que contém widgets e ferramentas para a implementação de designs de aplicativos com base no Material Design.

### `ListaTransferencias` é responsável por exibir uma lista de transferências e permitir que o usuário adicione novas transferências. 

1. **Definição da classe `ListaTransferencias`:**
    - Estende `StatefulWidget`, indicando que este widget pode ter seu estado alterado dinamicamente.

2. **Inicialização da lista de transferências:**
    - A lista `_transferencias` é inicializada como uma lista vazia.

3. **Método `createState`:**
    - Retorna uma instância de `ListaTransferenciasState`, que gerencia o estado do widget `ListaTransferencias`.

4. **Classe `ListaTransferenciasState`:**
    - Estende `State<ListaTransferencias>`, indicando que esta classe gerencia o estado do widget `ListaTransferencias`.

5. **Método `build`:**
    - Retorna um `Scaffold` que contém uma `AppBar` com o título "Transferências", uma `ListView.builder` para exibir a lista de transferências e um `FloatingActionButton` para adicionar novas transferências.
    - O `ListView.builder` cria os itens da lista com base no tamanho da lista `_transferencias`, e para cada item, cria um `ItemTransferencia` passando a transferência correspondente.
    - O `FloatingActionButton` tem um ícone de adição e, quando pressionado, abre o formulário de transferência. Após a transferência ser concluída, o método `_atualiza` é chamado para adicionar a nova transferência à lista.

6. **Método `_atualiza`:**
    - Adiciona a transferência recebida à lista `_transferencias` e atualiza o estado do widget.

7. **Classe `ItemTransferencia`:**
    - Um widget que representa visualmente uma transferência na lista. Ele exibe o valor e o número da conta da transferência em um `Card` com um `ListTile`.



### `FormularioTransferencia`,  é responsável por criar um formulário para que o usuário insira os detalhes de uma nova transferência.

1. **Definição da classe `FormularioTransferencia`:**
    - Estende `StatefulWidget`, indicando que este widget pode ter seu estado alterado dinamicamente.

2. **Método `createState`:**
    - Retorna uma instância de `FormularioTransferenciaState`, que gerencia o estado do widget `FormularioTransferencia`.

3. **Classe `FormularioTransferenciaState`:**
    - Estende `State<FormularioTransferencia>`, indicando que esta classe gerencia o estado do widget `FormularioTransferencia`.
    - Possui dois controladores de campo de texto para capturar o número da conta e o valor da transferência.

4. **Método `build`:**
    - Retorna um `Scaffold` que contém uma `AppBar` com o título "Criando Transferência" e um `Column` com os seguintes elementos:
        - Dois widgets `Editor` para capturar o número da conta e o valor da transferência. Os valores dos campos são controlados pelos controladores `_controladorCampoNumeroConta` e `_controladorCampoValor`. Cada `Editor` possui um ícone associado.
        - Um `ElevatedButton` com o texto "Confirmar", que, quando pressionado, chama o método `_criaTransferencia`.

5. **Método `_criaTransferencia`:**
    - Converte os valores inseridos nos campos de texto em números inteiros (para o número da conta) e números de ponto flutuante (para o valor da transferência).
    - Se ambos os valores forem válidos (diferentes de `null`), cria uma nova instância da classe `Transferencia` com esses valores e fecha o formulário, passando a nova transferência de volta para a tela anterior.

