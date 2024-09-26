# DIO - Trilha .NET - Fundamentos
www.dio.me

## Desafio de projeto
Para este desafio, você precisará usar seus conhecimentos adquiridos no módulo de fundamentos, da trilha .NET da DIO.

## Contexto
Você foi contratado para construir um sistema para um estacionamento, que será usado para gerenciar os veículos estacionados e realizar suas operações, como por exemplo adicionar um veículo, remover um veículo (e exibir o valor cobrado durante o período) e listar os veículos.

## Proposta
Você precisará construir uma classe chamada "Estacionamento", conforme o diagrama abaixo:
![Diagrama de classe estacionamento](diagrama_classe_estacionamento.png)

A classe contém três variáveis, sendo:

**precoInicial**: Tipo decimal. É o preço cobrado para deixar seu veículo estacionado.

**precoPorHora**: Tipo decimal. É o preço por hora que o veículo permanecer estacionado.

**veiculos**: É uma lista de string, representando uma coleção de veículos estacionados. Contém apenas a placa do veículo.

A classe contém três métodos, sendo:

**AdicionarVeiculo**: Método responsável por receber uma placa digitada pelo usuário e guardar na variável **veiculos**.

**RemoverVeiculo**: Método responsável por verificar se um determinado veículo está estacionado, e caso positivo, irá pedir a quantidade de horas que ele permaneceu no estacionamento. Após isso, realiza o seguinte cálculo: **precoInicial** * **precoPorHora**, exibindo para o usuário.

**ListarVeiculos**: Lista todos os veículos presentes atualmente no estacionamento. Caso não haja nenhum, exibir a mensagem "Não há veículos estacionados".

Por último, deverá ser feito um menu interativo com as seguintes ações implementadas:
1. Cadastrar veículo
2. Remover veículo
3. Listar veículos
4. Encerrar


## Solução
O código está pela metade, e você deverá dar continuidade obedecendo as regras descritas acima, para que no final, tenhamos um programa funcional. Procure pela palavra comentada "TODO" no código, em seguida, implemente conforme as regras acima.


## Implementações

### Alterações realizadas:
**AdicionarVeiculo:** Adicionei a lógica para pedir a placa ao usuário e armazená-la na lista de veículos.
**RemoverVeiculo:** Pedi ao usuário a quantidade de horas que o veículo ficou estacionado, calculei o valor total e removi o veículo da lista.
**ListarVeiculos:** Verifica se existem veículos na lista e os exibe.

### O que foi adicionado:
Antes de adicionar a placa à lista de veículos, o código agora verifica se a placa já está cadastrada usando **Any()** para comparar a placa (ignorando diferenças de maiúsculas/minúsculas). Se a placa já estiver presente, exibe uma mensagem informando que o veículo já está estacionado e não o adiciona novamente.
Com isso, você garante que não haverá duplicação de placas no estacionamento.

### Melhorias detalhadas:
**Validação de Entrada:**
1. No método *AdicionarVeiculo*, agora verificamos se a placa não é uma string vazia ou nula com string.IsNullOrWhiteSpace().
2. No método *RemoverVeiculo*, validamos se a quantidade de horas digitada é um número válido e positivo usando **int.TryParse().**

**Tratamento de Exceções (indireto):**
Embora não tenha um bloco **try-catch** explícito, o uso de **int.TryParse()** ajuda a evitar exceções durante a conversão da string para número. Caso o usuário digite algo inválido, ele será avisado sem que o programa quebre.

**Normalização da Placa:**
A placa é armazenada em letras maiúsculas com **ToUpper()** para garantir que comparações sejam feitas de maneira uniforme.

**Mensagens mais Amigáveis:**
Mensagens claras foram adicionadas para que o usuário entenda o que aconteceu durante a execução de cada operação.

**Listagem de Veículos:**
Ao listar os veículos, agora mostramos o número total de veículos estacionados.
